<template>
  <div class="">
<div class="login-page">
    
<div class="  md:mx-16 mx-4 lg:mx-20 shadow-2xl grid grid-cols-1 gap-2 rounded-md border border-4 p-4 bg-grey-300">
<div class="">
        <img src="@/assets/images/user.png" alt="" class="w-10 h-10 mx-20 ">
    </div>
<div class="">username and password</div>
<div class="">remberpassword</div>
<div class="">forget password and already a user</div>
</div>
</div>
  </div>
</template>

<script>
export default {
name: "Login",
}
</script>

<style scoped>
.login-page{
margin-top:15%;
text-align:center;
}
.bg-grey-300{
    background-color: rgba(250, 249, 249, 0.534);
}
</style>