<template>
  <div class="flex flex-row px-4 items-start">
    <img
      src="../assets/profile.svg"
      alt="User Profile"
      class="userprofile w-12 rounded-full"
    />
    <div class="pl-4 pt-2">
      <div class="text-start flex flex-row">
        <h3 class="username">
          {{ comment.user }}
        </h3>
        <div class="relative w-4 pl-2 ml-2" v-if="comment.varified">
          <img
            class="absolute top-0 left-0"
            src="../assets/ellipse.svg"
            alt="Workplace"
            width="600"
          />

          <img
            class="cursor-pointer absolute top-0 left-0 p-[4px] hover:shadow-outline"
            src="../assets/check_small.svg"
            width="600"
          />
        </div>
        <span class="text-gray-500 text-[13px] leading-none">1일전 </span>
      </div>
      <div class="flex flex-col mt-2">
        <p class="text-gray-600 text-sm font-Noto">
          {{ comment.text }}
        </p>
        <Actions :actions="comment.actions" class="my-4" />
      </div>
    </div>
    <div class="ml-auto">
      <div class="flex items-center space-x-2 cursor-pointer">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          fill="none"
          viewBox="0 0 24 24"
          stroke-width="1.5"
          stroke="currentColor"
          class="w-6 h-6"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            d="M6.75 12a.75.75 0 11-1.5 0 .75.75 0 011.5 0zM12.75 12a.75.75 0 11-1.5 0 .75.75 0 011.5 0zM18.75 12a.75.75 0 11-1.5 0 .75.75 0 011.5 0z"
          />
        </svg>
      </div>
    </div>
  </div>
</template>

<script setup>
const props = defineProps(["comment"]);
</script>
