<script setup>
import{ Link }from '@inertiajs/inertia-vue3';

defineProps({
  blogs: Array
})
</script>

<template>
<div v-if="$page.props.flash.message" class="bg-blue-300">
  {{ $page.props.flash.message }}
</div>
<ul>
  <li v-for="blog in blogs" :key="blog.id" class="mb-4">
  <div>
    <span class="font-bold">件名：</span>
    <Link class="text-blue-400" :href="route('inertia.show', { id: blog.id })">
      {{ blog.title }}
    </Link>
  </div>
  <div>
    <span class="font-bold">本文：</span>
    {{ blog.content }}
  </div>
</li>
</ul>
</template>
