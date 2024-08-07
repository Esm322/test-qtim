<template>
  <li class="articles__item">
    <article class="articles__article article">
      <img class="article__img" :src="props.img" :alt="props.title">
      <p class="article__text">
        {{ props.preview }}
      </p>
      <NuxtLink :to="{ name: 'Post', params: { id } }" class="article__btn-more btn-reset">
        Read more
      </NuxtLink>
    </article>
  </li>
</template>

<script setup lang="ts">
const props = defineProps<{
  img: string,
  title: string,
  preview: string,
  id: string,
}>();
</script>
