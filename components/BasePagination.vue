<template>
  <ul class="articles__pagination list-reset">
    <li class="articles__page prepage" v-show="props.page > 1">
      <a class="articles__link-page link-prepage" @click.prevent="prePage">
        <img src="/assets/img/Vector 35.svg" alt="previos" class="articles__link-pre-img">
      </a>
    </li>
    <li class="articles__page" v-for="pageNumber in props.pagesCount" :key="pageNumber">
      <a class="articles__link-page" :class="{ 'articles__link-page--current': props.page === pageNumber }"
        @click.prevent="paginate(pageNumber)">
        {{ pageNumber }}
      </a>
    </li>
    <li class="articles__page nextpage" v-show="props.page !== props.pagesCount">
      <a class="articles__link-page link-nextpage" @click.prevent="nextPage">
        <img src="/assets/img/Vector 35.svg" alt="next" class="articles__link-img">
      </a>
    </li>
  </ul>
</template>


<script setup lang="ts">
import { ref, watch } from 'vue';

const props = defineProps<{
  page: number,
  offset: number,
  postsPerPage: number,
  pagesCount: number,
}>();

const emits = defineEmits<{
  (event: 'update:page', value: number): void,
  (event: 'update:offset', value: number): void,
}>();

const currPage = ref<number>(1);
const currOffset = ref<number>(0);

const prePage = (): void => emits('update:page', currPage.value -= 1);
const nextPage = (): void => emits('update:page', currPage.value += 1);
const paginate = (page: number): void => emits('update:page', currPage.value = page);

watch(currPage, (newValue: number): void => {
  if (newValue) {
    emits('update:offset', currOffset.value = newValue * props.postsPerPage);
  }
})
</script>
