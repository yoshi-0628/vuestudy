<template>
  <div class="container">
    <h2>Login to Feedly</h2>

    <form method="post">
      <input
        type="email"
        autocapitalize="off"
        autocorrect="off"
        name="login"
        class="input-text input-top"
        placeholder="Email"
        required=""
        value=""
      />
      <input
        type="password"
        autocapitalize="off"
        autocorrect="off"
        name="password"
        class="input-text input-bottom"
        placeholder="Password"
        required=""
      />
      <input type="hidden" name="csrfToken" value="l1550s:1613570465018" />
      <input type="submit" class="button" value="Login" />
    </form>
    <div class="footer">
      <a class="lnk" href="#">Forgot your password?</a>
      <a class="lnk" href="#">sign up</a>
    </div>
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";

export default {
  name: "App",
  components: {
    HelloWorld,
  },
};
</script>

<style>
</style>
