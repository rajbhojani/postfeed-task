<template>
  <div class="flex h-screen">
    <div
      class="m-auto w-[350px] bg-[#F5F5F5] flex flex-col items-center justify-center h-screen border-slate-500 border-solid border-1"
    >
      <Header />
      <slot />
      <Footer />
    </div>
  </div>
</template>
