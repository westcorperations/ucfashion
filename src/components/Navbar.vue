<template>
  <!-- navbar -->
  <nav class="bg-white top-0 mt-0 fixed w-full z-10 shadow-lg">
    <div class="max-w-6xl mx-auto px-4">
      <div class="flex justify-between">
        <div class="flex space-x-7">
          <!-- logo -->
          <div>
            <a href="#" class="flex items-center py-4 px-2">
              <!-- <img
                src="../assets/images/fashion.svg"
                alt="Logo"
              /> -->
              <span class=" logo font-black filter drop-shadow-xl  text-white ">UCFASHION</span>
            </a>
          </div>
          <!-- primary navbar items -->
          <div class="hidden md:flex items-center space-x-1">
            <router-link
              :to="{ name: 'Home' }"
              class="
                py-4
                px-2
                text-green-500
                border-b-4
                font-semibold
                hover:text-green-500
                transition
                duration-300
              "
              >Home</router-link
            >
            <a href="#"
              
              class="
                py-4
                px-2
                text-green-500
                border-b-4
                font-semibold
                hover:text-green-500
                transition
                duration-300
              "
              >About</a
            >
            <a
              href="#"
              class="
                py-4
                px-2
                text-green-500
                border-b-4
                font-semibold
                hover:text-green-500
                transition
                duration-300
              "
              >contant</a
            >
            <a
              href="#"
              class="
                py-4
                px-2
                text-green-500
                border-b-4
                font-semibold
                hover:text-green-500
                transition
                duration-300
              "
              >products</a
            >
          </div>
        </div>

        <!-- secoundary navbar items -->
        <div class="hidden md:flex items-center space-x-3">
          <router-link
          :to="{name: 'Login' }"
            href="#"
            class="
              py-2
              px-2
              font-medium
              text-grey-500
              rounded
              hover:bg-green-500
              hover:text-white
              transition
              duration-300
            "
            >Login</router-link>
          
          <a
            href="#"
            class="
              py-2
              px-2
              font-medium
              text-grey-500
              rounded
              hover:bg-green-500
              hover:text-white
              transition
              duration-300
            "
            >Sign Up</a
          >
          <a
            title="wistlist"
            href="#"
            class="
              relative
              flex
              py-4
              px-2
              font-medium
              text-black-500
              rounded
              hover:bg-green-500
              hover:text-white
              transition
              duration-300
            "
          >
            <img
              src="../assets/images/wishlist.svg"
              alt="Wishlist"
              class="h-6 w-7 fill-current"
            />
            <span
              class="
                absolute
                right-0
                top-0
                rounded-full
                bg-red-600
                w-4
                h-4
                top
                right
                p-0
                m-0
                text-white
                font-mono
                text-sm
                leading-tight
                text-center
              "
            >
              5
            </span>
          </a>
          <a
            href="#"
            class="
              relative
              flex
              py-4
              px-2
              text-black-500
              rounded
              hover:bg-green-500
              hover:text-white
              transition
              duration-300
            "
          >
            <img
              title="Cart"
              src="../assets/images/shopping-cart.svg"
              alt="Cart"
              class="h-7 w-7 fill-current"
            />
            <span
              class="
                absolute
                right-0
                top-0
                rounded-full
                bg-red-600
                w-4
                h-4
                top
                right
                p-0
                m-0
                text-white
                font-mono
                text-sm
                leading-tight
                text-center
              "
            >
              5
            </span>
          </a>
        </div>
        <!-- Mobile menu buttons -->
        <!--Mobile wish list icon  -->
        <div class="md:hidden flex items-center">
          <div>
            <a href="#" class="flex relative items-center py-4 px-2">
              <img
                src="../assets/images/wishlist.svg"
                alt="Logo"
                class="h-5 w-5 mr-2"
              />
              <span
                class="
                  absolute
                  right-0
                  top-0
                  rounded-full
                  bg-red-600
                  w-4
                  h-4
                  top
                  right
                  p-0
                  m-0
                  text-white
                  font-mono
                  text-sm
                  leading-tight
                  text-center
                "
              >
                5
              </span>
            </a>
          </div>
          <!-- Mobile Cart  icon-->
          <a href="#" class="flex relative items-center py-4 px-2">
            <img
              src="../assets/images/shopping-cart.svg"
              alt="Logo"
              class="h-5 w-5 mr-2"
            />
            <span
              class="
                absolute
                right-0
                top-0
                rounded-full
                bg-red-600
                w-4
                h-4
                top
                right
                p-0
                m-0
                text-white
                font-mono
                text-sm
                leading-tight
                text-center
              "
            >
              5
            </span>
          </a>

          <button
            @click="ToggleNav"
            class="outline-none ml-3 mobile-menu-button"
          >
            <svg
              class="fill-current h-6 w-6"
              viewBox="0 0 20 20"
              xmlns="http://www.w3.org/2000/svg"
            >
              <title>Menu</title>
              <path d="M0 3h20v2H0V3zm0 6h20v2H0V9zm0 6h20v2H0v-2z" />
            </svg>
          </button>
        </div>
      </div>
    </div>
    <!-- mobile menu -->
    <div v-if="toggleNav" class="mobile-menu">
      <ul class="">
        <li class="">
          <router-link
            :to="{ name: 'Home' }"
            class="
              block
              text-sm
              px-2
              py-4
              hover:bg-green-500
              transition
              duration-300
            "
          >
            Home</router-link
          >
        </li>
        
        <li class="">
          <a
            href="#"
            class="
              block
              text-sm
              px-2
              py-4
              hover:bg-green-500
              transition
              duration-300
            "
            >Contact Us</a
          >
        </li>
        <li class="">
          <a
            href="#"
            class="
              block
              text-sm
              px-2
              py-4
              hover:bg-green-500
              transition
              duration-300
            "
            >Products</a
          >
        </li>
        <li class="">
          <a
            href="#"
            class="
              block
              text-sm
              px-2
              py-4
              hover:bg-green-500
              transition
              duration-300
            "
            >SignIn</a
          >
        </li>
        <li class="">
          <router-link
        :to="{name: 'Login'}"
            class="
              block
              text-sm
              px-2
              py-4
              hover:bg-green-500
              transition
              duration-300
            "
            >Login</router-link
          >
        </li>
      </ul>
    </div>
  </nav>
</template>

<script>
export default {
  data() {
    return {
      toggleNav: false,
    };
  },
  methods: {
    ToggleNav() {
      this.toggleNav = !this.toggleNav;
    },
  },
};
</script>

<style scoped>
a.router-link-active,
.router-link-exact-active {
  color: green;
  text-shadow: 1px 1px 1px black;
  cursor: pointer;
  border-bottom: 2px solid green;
}
.logo{
  text-shadow: 2px 2px 6px black;
}

</style>