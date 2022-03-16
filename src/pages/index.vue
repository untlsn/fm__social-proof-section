<script setup lang="ts">
import Ranking from '~/components/organisms/Ranking.vue';
import Comment from '~/components/organisms/Comment.vue';
import anne from '~/assets/image-anne.jpg';
import colton from '~/assets/image-colton.jpg';
import irene from '~/assets/image-irene.jpg';

const rankings = [
  { stars: 5, where: 'Reviews' },
  { stars: 5, where: 'Report Guru' },
  { stars: 5, where: 'BestTech' },
];
const comments = [
  {
    author: 'Colton Smith',
    image: colton,
    comment: 'We needed the same printed design as the one we had ordered a week prior. Not only did they find the original order, but we also received it in time. Excellent!'
  },
  {
    author: 'Irene Roberts',
    image: irene,
    comment: 'Customer service is always excellent and very quick turn around. Completely delighted with the simplicity of the purchase and the speed of delivery.'
  },
  {
    author: 'Anne Wallace',
    image: anne,
    comment: 'Put an order with this company and can only praise them for the very high standard. Will definitely use them again and recommend them to everyone!'
  },
];

</script>

<template>
  <main class="p-8 text-center grid-cols-2 grid-rows-2 gap-20 lg:(grid p-40 text-left) space-y-12">
    <div class="lg:w-120">
      <h1 class="text-6xl text-purple font-bold">
        10,000+ of our users love our products.
      </h1>
      <p class="text-gray-text mt-6">
        We only provide great products combined with excellent customer service.
        See what our satisfied customers are saying about our services.
      </p>
    </div>
    <div class="space-y-4">
      <Ranking
        v-for="(rank, index) in rankings"
        :key="rank.where"
        :style="{ '--left': `${index*3}rem` }"
        class="space-left"
        v-bind="rank"
      />
    </div>
    <div class="flex flex-col lg:flex-row gap-4 justify-center col-span-2">
      <Comment
        v-for="(comment, index) in comments"
        :key="comment.author"
        :author="comment.author"
        :img-src="comment.image"
        :style="{ '--top': `${index}rem` }"
        class="space-top"
      >
        {{ comment.comment }}
      </Comment>
    </div>
  </main>
</template>

<style>
@media (min-width: 1024px) {
  .space-left {
    --left: '0';
    margin-left: var(--left);
  }

  .space-top {
    --top: '0';
    margin-top: var(--top);
  }
}

</style>
