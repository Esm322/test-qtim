<template>
  <ul class="articles__list list-reset">
    <PostItem v-for="post in props.posts" :key="post.id"
      :img="post.image"
      :title="post.title"
      :preview="post.preview"
      :id="post.id"
    />
  </ul>
</template>

<script setup lang="ts">
import type { IArticle } from '~/interfaces/articles';

const props = defineProps<{
  posts: IArticle[],
}>();
</script>
