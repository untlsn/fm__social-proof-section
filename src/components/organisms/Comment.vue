<script lang="ts" setup="">
defineProps<{
  author: string,
  imgSrc: string,
}>();
</script>

<template>
  <article class="bg-purple text-white p-12 rounded-xl h-60 lg:w-100">
    <h1 class="flex items-center pb-4 gap-4">
      <img :src="imgSrc" alt="author image" class="rounded-full h-12">
      <div>
        <p class="font-bold">
          {{ author }}
        </p>
        <p class="text-light-purple">
          Verified Buyer
        </p>
      </div>
    </h1>
    <div>
      "
      <slot/>
      "
    </div>
  </article>
</template>
