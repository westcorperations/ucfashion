<template>
  <div class="home h-screen">
    <!-- carosel  component-->
    <Carosel
      :navigation="true"
      :pagination="true"
      :startAutoPlay="true"
      :timeout="6000"
      class="h-2/3 md:h-4/5 left-0 relative -top-0"
      v-slot="{ currentSlide }"
    >
      <Slide v-for="(slide, index) in caroselSlides" :key="index">
        <div v-show="currentSlide === index + 1" class="slide-info">
          <img
            :src="require('@/assets/images/' + slide + '.jpg')"
            class="w-full h-full absolute object-scale dark"
          />
        </div>
      </Slide>
    </Carosel>
    <!--  Home producs display -->

    <div class="my-2 ">
      <div
        class="
          text-center
          font-black
          mx-auto
          lg:text-xl
          text-sm text-green-500
          flex
          justify-evenly
        "
      >
        <div>
          <h2
            :class="HotDeals ? 'border-red-900' : 'border-green-900'"
            class="border-b-2 tracker-wide cursor-pointer"
            @click="DisplayHotdeals"
          >
            Hot Deals
          </h2>
        </div>
        <div>
          <h2
            :class="Male ? 'border-red-900' : 'border-green-900'"
            class="border-b-2 tracker-wide cursor-pointer"
            @click="DisplayMale"
          >
            Men Wares
          </h2>
        </div>
        <div>
          <h2
            :class="Female ? 'border-red-900' : 'border-green-900'"
            class="border-b-2 tracker-wide cursor-pointer"
            @click="DisplayFemale"
          >
            Female Wares
          </h2>
        </div>
      </div>
      <div class="container w-full bg-black-600">
        <!-- Hot deals -->
        <div
          class="grid md:grid-cols-4 lg:grid-cols-8 grid-cols-2 lg:ml-16 gap-4"
        >
          <div
            v-show="HotDeals"
            class="
              card
              bg-white
              shadow-2xl
              flex
              justify-between
              flex-col
              rounded-md
              overflow-hidden
              cursor-pointer
            "
            v-for="Product in Products"
            :key="Product.id"
          >
            <div class="imgBx w-full p-5 transform hover:scale-110">
              <!-- product image -->
              <img
                :src="require('@/assets/images/' + Product.image + '.png')"
                alt=""
              />
            </div>
            <h3 class="uppercase font-bold text-center text-sm">
              {{ Product.name }}
            </h3>
            <p class="text-center text-xs">
              Lorem ipsum dolor sit amet consectetur.
            </p>
            <div class="price text-sm font-bold text-red-500 text-center">
              ${{ Product.price }}
            </div>
            <!-- product rating -->
            <div class="flex flex-row justify-center mx-4">
              <img src="@/assets/images/star.svg" alt="" class="w-3 h-3" />
              <img src="@/assets/images/star.svg" alt="" class="w-3 h-3" />
              <img src="@/assets/images/star.svg" alt="" class="w-3 h-3" />
              <img src="@/assets/images/star.svg" alt="" class="w-3 h-3" />
            </div>
            <div
              class="
                bg-green-300
                font-bold
                text-center
                cursor-pointer
                transform
                hover:scale-110
                rela
                buttom-0
              "
            >
              Add to cart
            </div>
          </div>
        </div>

        <!-- male products -->
        <div
          class="grid md:grid-cols-4 lg:grid-cols-8 grid-cols-2 lg:ml-16 gap-4"
        >
          <div
            v-show="Male"
            class="
              card
              bg-white
              shadow-2xl
              flex
              justify-between
              flex-col
              rounded-md
              overflow-hidden
              cursor-pointer
            "
            v-for="MenWare in MenWares"
            :key="MenWare.id"
          >
            <div class="imgBx w-full p-5 transform hover:scale-110">
              <!-- product image -->
              <img
                :src="require('@/assets/images/' + MenWare.image + '.png')"
                alt=""
              />
            </div>
            <h3 class="uppercase font-bold text-center text-sm">
              {{ MenWare.name }}
            </h3>
            <p class="text-center text-xs">
              Lorem ipsum dolor sit amet consectetur.
            </p>
            <div class="price text-sm font-bold text-red-500 text-center">
              ${{ MenWare.price }}
            </div>
            <!-- product rating -->
            <div class="flex flex-row justify-center mx-4">
              <img src="@/assets/images/star.svg" alt="" class="w-3 h-3" />
              <img src="@/assets/images/star.svg" alt="" class="w-3 h-3" />
              <img src="@/assets/images/star.svg" alt="" class="w-3 h-3" />
              <img src="@/assets/images/star.svg" alt="" class="w-3 h-3" />
            </div>
            <div
              class="
                bg-green-300
                font-bold
                text-center
                cursor-pointer
                transform
                hover:scale-110
                rela
                buttom-0
              "
            >
              Add to cart
            </div>
          </div>
        </div>

        <!-- female wares -->
        <div
          class="grid md:grid-cols-4 lg:grid-cols-8 grid-cols-2 lg:ml-16 gap-4"
        >
          <div
            v-show="Female"
            class="
              card
              bg-white
              shadow-2xl
              flex
              justify-between
              flex-col
              rounded-md
              overflow-hidden
              cursor-pointer
            "
            v-for="FemaleWare in FemaleWares"
            :key="FemaleWare.id"
          >
            <div class="imgBx w-full p-5 transform hover:scale-110">
              <!-- product image -->
              <img
                :src="require('@/assets/images/' + FemaleWare.image + '.png')"
                alt=""
              />
            </div>
            <h3 class="uppercase font-bold text-center text-sm">
              {{ FemaleWare.name }}
            </h3>
            <p class="text-center text-xs">
              Lorem ipsum dolor sit amet consectetur.
            </p>
            <div class="price text-sm font-bold text-red-500 text-center">
              ${{ FemaleWare.price }}
            </div>
            <!-- product rating -->
            <div class="flex flex-row justify-center mx-4">
              <img src="@/assets/images/star.svg" alt="" class="w-3 h-3" />
              <img src="@/assets/images/star.svg" alt="" class="w-3 h-3" />
              <img src="@/assets/images/star.svg" alt="" class="w-3 h-3" />
              <img src="@/assets/images/star.svg" alt="" class="w-3 h-3" />
            </div>
            <div
              class="
                bg-green-300
                font-bold
                text-center
                cursor-pointer
                transform
                hover:scale-110
                rela
                buttom-0
              "
            >
              Add to cart
            </div>
          </div>
        </div>
      </div>
    </div>


<!-- About us -->
<div class=" mx-4 my-2">
<div class="grid md:grid-cols-3 lg:grid-cols-3 grid-cols-1 gap-8 w-full ">
<div class=" flex justify-between rounded-md  bg-grey-500 flex-col bg-white shadow-2xl border border-solid-8 border-blue-500 drop-shadow p-4">
<div class="font-bold text-xs lg:text-sm text-center">
  What is UcFashion?
</div>
<div>
  <p class="text-xs serif ">Uc fashion house is a high class affordable fashion store.
    Consider yourself a perfect model because
    uc fashion gives you top notch fashion designs from all around the globe
  </p>
</div>
</div>



<div class=" flex justify-between  rounded-md flex-col bg-white shadow-2xl border border-solid-8 border-blue-500 drop-shadow p-4">
<div class="font-bold text-xs lg:text-sm text-center">
  When do i get my goods?
</div>
<div>
  <p class="text-xs serif ">
    uc fashion provides fastdelivery service depending on the location
    consider us the top dog when it comes to cheeter delivery to your doorstep
    which is also for free for most goods.
  </p>
</div>
</div>


<div class=" flex justify-between rounded-md flex-col bg-white shadow-2xl border border-solid-10 border-green-500 drop-shadow p-4">
<div class="font-bold text-xs lg:text-sm text-center">
  How do we treat our customers?
</div>
<div>
  <p class="text-xs serif ">
    uc fashion store provides friendly customer first service.
    24/7 customer service is also available enjoy fun shopping with friendly customer service to guild you
  </p>
</div>
</div>
</div>

</div>

<div id="  ">
  <Footer></Footer>
</div>
  </div>
</template>


<script>
import { ref } from "@vue/reactivity";
import Carosel from "../components/Carosel.vue";
import Slide from "../components/Slide.vue";
import  Footer from '@/components/Footer.vue';

export default {
  name: "Home",
  components: { Carosel, Slide, Footer },
  setup() {
    const caroselSlides = ["carosel1", "carosel2", "carosel3"];
    const Products = [
      { id: "1", image: "product1", name: "product1", price: "200.00" },
      { id: "2", image: "product2", name: "product2", price: "100.99" },
      { id: "3", image: "product3", name: "product3", price: "150.00" },
      { id: "4", image: "product4", name: "product4", price: "300.00" },
      { id: "5", image: "product1", name: "product5", price: "200.99" },
      { id: "6", image: "product2", name: "product6", price: "300.00" },
      { id: "7", image: "product3", name: "product7", price: "600.25" },
      { id: "8", image: "product4", name: "product8", price: "99.99" },
    ];
    const MenWares = [
      { id: "2", image: "product2", name: "product2", price: "100.99" },
      { id: "3", image: "product3", name: "product3", price: "150.00" },
      { id: "4", image: "product4", name: "product4", price: "300.00" },
      { id: "9", image: "product4", name: "product9", price: "800.00" },
      { id: "10", image: "product5", name: "product10", price: "1000.00" },
      { id: "11", image: "product6", name: "product11", price: "300.99" },
      { id: "12", image: "product2", name: "product12", price: "900.99" },
      { id: "13", image: "product5", name: "product10", price: "1000.00" },
    ];

    const FemaleWares = [
      { id: "14", image: "product2", name: "product2", price: "100.99" },
      { id: "15", image: "product5", name: "product11", price: "150.00" },
      { id: "16", image: "product6", name: "product12", price: "300.00" },
      { id: "17", image: "product4", name: "product13", price: "800.00" },
      { id: "18", image: "product3", name: "product15", price: "1000.00" },
      { id: "19", image: "product2", name: "product14", price: "300.99" },
      { id: "20", image: "product3", name: "product16", price: "900.99" },
      { id: "21", image: "product6", name: "product17", price: "1000.00" },
    ];

    const Male = ref(false);
    const Female = ref(false);
    const HotDeals = ref(true);

    // toggl HotDeals
    const DisplayHotdeals = () => {
      HotDeals.value = true;
      Female.value = false;
      Male.value = false;

      return;
    };
    // toggle to female goods
    const DisplayFemale = () => {
      HotDeals.value = false;
      Female.value = true;
      Male.value = false;

      return;
    };
    // toggle to male goods
    const DisplayMale = () => {
      HotDeals.value = false;
      Female.value = false;
      Male.value = true;

      return;
    };
    return {
      caroselSlides,
      Products,
      Male,
      Female,
      HotDeals,
      DisplayFemale,
      DisplayHotdeals,
      DisplayMale,
      FemaleWares,
      MenWares,
    };
  },
};
</script>

<style scoped>
.home {
  margin-top: 60px;
  height:100%;
}
</style>