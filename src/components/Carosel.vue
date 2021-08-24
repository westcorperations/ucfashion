<template>
  <div class="carosel ">
    <slot :currentSlide="currentSlide" />
    <!-- Navigation -->
    <div
    v-if="navEnabled"
      class="
        Navigate
        w-full
        px-0
        py-4
        h-full
        absolute
        flex
        justify-center
        items-center
      "
    >
      <div
        @click="prevSlide"
        class="toggle-page left text-5xl text-white flex flex-1"
      >
        <h1
          class="
            flex
            items-center
            text-green-500
            shadow-xl
            cursor-pointer
            justify-center
            bg-0
            rounded-full
            w-10
            h-10
          "
        >
          &#8249;
        </h1>
      </div>
      <div
        @click="nextSlide"
        class="toggle-page right text-5xl text-white flex justify-end"
      >
        <h1
          class="
            flex
            items-center
            cursor-pointer
            text-green-500
            shadow-xl
            justify-center
            bg-0
            rounded-full
            w-10
            h-10
          "
        >
          &#8250;
        </h1>
      </div>
    </div>
    <!-- Pagination -->
    <div
      v-if="paginationEnabled"
      class="
        pagination
        absolute
        bottom-4
        md:bottom-4
        w-full
        flex
        justify-center
        items-center
        gap-5
      "
    >
      <span
        v-for="(slide, index) in getSlideCount"
        :key="index"
        :class="{ active: index + 1 === currentSlide }"
        class="cursor-pointer w-5 h-5 rounded-full bg-white shadow-xl"
        @click="goToSlide(index)"
      >
      </span>
    </div>
  </div>
</template>

<script>
import { ref } from "@vue/reactivity";
import { onMounted } from "@vue/runtime-core";
export default {
  props: ["startAutoPlay", "timeout", "navigation", "pagination"],
  setup(props) {
    const currentSlide = ref(1);
    const getSlideCount = ref(null);
    const autoPlayEnabled = ref(props.startAutoPlay === undefined ? 6000 : props.startAutoPlay);
    const timeoutDuration = ref(props.timeout === undefined ? true : props.timeout);
    const paginationEnabled = ref(props.pagination === undefined ? true : props.pagination);
    const navEnabled = ref(
      props.navigation === undefined ? true : props.navigation 
    );

    // next slide
    const nextSlide = () => {
      if (currentSlide.value === getSlideCount.value) {
        currentSlide.value = 1;
        return;
      }
      currentSlide.value += 1;
    };
    // prev slide
    const prevSlide = () => {
      if (currentSlide.value === 1) {
        currentSlide.value = 1;
        return;
      }
      currentSlide.value -= 1;
    };
    const goToSlide = (index) => {
      currentSlide.value = index + 1;
    };
    // auto play
    const autoPlay = () => {
      setInterval(() => {
        nextSlide();
      }, timeoutDuration.value);
    };
    if (autoPlayEnabled.value) {
      autoPlay();
    }

    onMounted(() => {
      getSlideCount.value = document.querySelectorAll(".slide").length;
    });

    return {
      currentSlide,
      getSlideCount,
      nextSlide,
      prevSlide,
      goToSlide,
      autoPlayEnabled,
      autoPlay,
      timeoutDuration,
      paginationEnabled,
      navEnabled,
    };
  },
};
</script>

<style scoped>
.active {
  background-color: green;
}
</style>