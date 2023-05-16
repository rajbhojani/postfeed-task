<template>
  <div class="flex flex-row px-4 items-center">
    <img
      src="../assets/profile.svg"
      alt="User Profile"
      class="userprofile w-12 rounded-full"
    />
    <div class="pl-4 pt-2">
      <div class="flex flex-row">
        <h3 class="text-center username">
          {{ user.name }}
        </h3>
        <div class="relative w-4 pl-2 ml-2">
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
        <span class="text-center text-gray-500 text-[13px] leading-none"
          >1일전
        </span>
      </div>
      <div class="flex items-center mt-0">
        <span class="text-gray-500 text-sm">{{ user.height }} cm</span>
        <span class="pb-2 mx-[2px] text-gray-500 text-sm"> . </span>
        <span class="text-gray-500 text-sm">{{ user.weight }} kg</span>
      </div>
    </div>
    <div class="ml-auto">
      <img src="../assets/ptag.svg" />
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      user: {
        name: "안녕 나 응애 ",
        height: "165",
        weight: "53",
      },
    };
  },
};
</script>
