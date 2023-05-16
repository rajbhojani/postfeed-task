<template>
  <div>
    <div v-for="post in posts" :key="post.id" class="rounded shadow">
      <User />
      <div class="posttext p-4">
        <strong>{{ post.heading }}</strong>
        <p class="mt-4 font-roboto" v-for="text in post.texts">
          {{ text }}
        </p>
      </div>
      <div class="ml-4 mb-4">
        <div
          v-for="tag in post.tags"
          :key="tag"
          class="posttag bg-gray-200 rounded-full py-1 px-3 font-roboto inline-block mt-2 mr-2"
        >
          {{ tag }}
        </div>
      </div>
      <div class="carousel">
        <img
          v-for="image in post.images"
          :src="image"
          :key="image"
          alt="Post Image"
          class="w-full"
        />
      </div>
      <Actions :actions="post.actions" class="pl-4 py-4 mb-4 bg-[#FFFFFF]" />
      <Comments :comments="post.comments" class="mt-4" />
    </div>
  </div>
</template>

<script setup>
const posts = ref([]);

posts.value = [
  {
    id: 1,
    heading: "지난 월요일에 했던 이벤트 중 가장 괜찮은 상품 뭐야?",
    texts: [
      "지난 월요일에 2023년 S/S 트렌드 알아보기 이벤트 참석했던 팝들아~혹시 어떤 상품이 제일 괜찮았어?",
      "후기 올라오는거 보면 로우라이즈? 그게 제일 반응 좋고 그 테이블이 제일 재밌었다던데 맞아???",
      " 올해 로우라이즈가 트렌드라길래 나도 도전해보고 싶은데 말라깽이가 아닌 사람들도 잘 어울릴지 너무너무 궁금해ㅜㅜ로우라이즈 테이블에 있었던 팝들 있으면 어땠는지 후기 좀 공유해주라~~!",
    ],
    tags: ["#2023", "#TODAYISMONDAY", "#TOP", "#POPS!", "#WOW", "#ROW"],
    images: [
      "https://wjddnjs754.cafe24.com/web/product/small/202303/5b9279582db2a92beb8db29fa1512ee9.jpg",
    ],
    actions: { like: 5, comments: 5, save: true, more: true },
    comments: [
      {
        user: "안녕 나 응애 ",
        varified: true,
        text: "어머 제가 있던 테이블이 제일 반응이 좋았나보네요🤭 우짤래미님도 아시겠지만 저도 일반인 몸매 그 이상도 이하도 아니잖아요?! 그런 제가 기꺼이 도전해봤는데 생각보다 괜찮았어요! 오늘 중으로 라이브 리뷰 올라온다고 하니 꼭 봐주세용~!",
        actions: { like: 5, comments: 5, save: false, more: false },
        replies: [
          {
            user: "ㅇㅅㅇ ",
            varified: false,
            text: "오 대박! 라이브 리뷰 오늘 올라온대요? 챙겨봐야겠다",
            actions: { like: 5, comments: 0, save: false, more: false },
          },
        ],
      },
    ],
  },
];
</script>

<style>
.username {
  height: 14px;
  font-style: normal;
  font-weight: 700;
  font-size: 14px;
  line-height: 100%;
  color: #1d232b;
}
.posttext {
  font-family: "Noto Sans";
  font-style: normal;
  font-weight: 500;
  font-size: 16px;
  line-height: 100%;
  /* or 12px */

  letter-spacing: -0.01em;

  /* N/9 */

  color: #313b49;

  /* Inside auto layout */

  flex: none;
  order: 1;
  flex-grow: 0;
}
.posttag {
  font-style: normal;
  font-weight: 600;
  font-size: 10px;
  line-height: 100%;
  /* identical to box height, or 12px */
  /* N/7 */
  color: #5a6b87;
}
</style>
