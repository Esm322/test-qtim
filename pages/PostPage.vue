<template>
  <main class="main">
    <section class="post">
      <div class="container post__container">
        <h2 class="post__title">
          {{ post?.title }}
        </h2>

        <div class="post__wrapper-about">
          <img :src="post?.image" :alt="post?.title" class="post__img">

          <h3 class="post__title-about">
            About
          </h3>

          <p class="post__text-about">
            {{ post?.description }}
          </p>
        </div>
      </div>
    </section>
  </main>
</template>

<script setup lang="ts">
import { ref, onMounted } from 'vue';

import axios, { type AxiosResponse } from 'axios';

import type { IArticle } from '~/interfaces/articles';

const route = useRoute();

const post = ref<IArticle | null>(null);

const loadPost = (): void => {
  axios.get(`https://6082e3545dbd2c001757abf5.mockapi.io/qtim-test-work/posts/${route.params.id}`)
    .then((response: AxiosResponse): void => post.value = response.data);
};

onMounted(() => {
  loadPost();
})
</script>
