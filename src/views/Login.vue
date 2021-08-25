<template>
  <div class="w-full max-w-xs login-page mx-auto">
    <form class="bgw-grey-300 shadow-md rounded px-8 pt-6 pb-8 mb-4">
      <div class="mb-4">
        <label
          for="username"
          class="block text-black text-sm font-bold mb-2"
    
          >Username</label
        >
        <input
          type="text"
          name=""
          id=""
          class="
            shadow
            appearance-none
            border
            rounded
            w-full
            py-2
            px-3
            text-grey-300
            leading-tight
            focus:outline-none
            focus:shadow-outline
          "
          placeholder="Username"
        />
      </div>
<div class="mb-4">
<label
          for="password"
          class="block text-black text-sm font-bold mb-2"
    
          >Password</label
        >
         <input
          type="password"
          name=""
          id=""
          class="
            shadow
            appearance-none
            border
            rounded
            w-full
            py-2
            px-3
            text-grey-300
            leading-tight
            focus:outline-none
            focus:shadow-outline
          "
          placeholder="********"
        />
</div>
<div class="w-full mb-2">
    <button class="bg-green-500 hover:bg-green-700 text-white font-bold w-full  py-2 px-4 rounded focus:outline-none 
    focus:shadow-outline" type="button">
        Sign In
    </button>
    </div>
    <div class="flex items-center justify-between">
    <a href="#" class="inline-block align-baseline font-bold text-sm text-green-700 hover:text-green-800">
        Forgot Password?
    </a>
    <a href="#" class="inline-block align-baseline font-bold text-sm text-green-700 hover:text-green-800">
        Create Account
    </a>
</div>

    </form>
  </div>
</template>

<script>
export default {
  name: "Login",
};
</script>

<style scoped>
.login-page {
  margin-top: 15%;
  text-align: center;
}
.bgw-grey-300 {
  background-color:lightgrey;
}
</style>