<template>
  <div v-for="comment in comments">
    <div class="flex items-start mb-4">
      <Comment :comment="comment" />
    </div>
    <div
      v-for="reply in comment.replies"
      class="pl-14 border-l-2 border-gray-300"
    >
      <Comment :comment="reply" />
    </div>
  </div>
</template>

<script setup>
const props = defineProps(["comments"]);
</script>
