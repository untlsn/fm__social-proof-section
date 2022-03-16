<script lang="ts" setup="">
import Star from '~/components/atoms/Star.vue';

defineProps<{
  stars: number
  where: string
}>();
</script>

<template>
  <article class="flex flex-col gap-2 items-center justify-evenly bg-gray-purple p-4 lg:(flex-row w-140) rounded">
    <div class="flex gap-2">
      <Star v-for="key in stars" :key="key"/>
    </div>
    <p class="font-bold text-purple">
      Ranked {{ stars }} Stars in {{ where }}
    </p>
  </article>
</template>
