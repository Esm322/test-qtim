<template>
  <main class="main">
    <section class="articles">
      <div class="container articles__container">
        <h2 class="articles__title">
          Articles
        </h2>

        <div class="wrapper-loading" v-if="isPostLoading">
          Loading...
          <div class="wrapper-loading spinner-3">
          </div>
        </div>

        <PostsList v-else :posts="posts" />

        <BasePagination v-model:page="page" v-model:offset="offset" :posts-per-page="postsPerPage"
          :pages-count="countPages" />

      </div>
    </section>
  </main>
</template>

<script setup lang="ts">
import { ref, computed, onMounted } from 'vue';

import axios, { type AxiosResponse } from 'axios';

import type { IArticle } from '~/interfaces/articles';

const BASE_URL = 'https://6082e3545dbd2c001757abf5.mockapi.io/qtim-test-work/posts/';

const postsData = ref<IArticle[]>([]);
const page = ref<number>(1);
const postsPerPage: number = 8;
const offset = ref<number>((page.value - 1) * postsPerPage);
const isPostLoading = ref<boolean>(false);

const posts = computed(() =>
  postsData.value ? postsData.value.slice(offset.value, offset.value + postsPerPage) : []);

const countPages = computed<number>((): number =>
  postsData.value ? Math.trunc(postsData.value.length / postsPerPage) : 0);

const loadPosts = (): void => {
  isPostLoading.value = true;

  axios.get(BASE_URL)
    .then((response: AxiosResponse): void => postsData.value = response.data)
    .catch((err: AxiosResponse) => {
      isPostLoading.value = false;
      console.log(err);
    })
    .finally(() => isPostLoading.value = false);
};

onMounted(() => {
  loadPosts();
})
</script>
