<template>
  <!-- component -->
  <div class="container flex mt-10">
    <div class="container signup mt-10">
      <div class="min-h-screen flex mb-4 row-signup">
        <div class="w-3/5 h-12 row-right">

          <div class="text-dig">
            <h1 class="w-full text-base sm:text-lg md:text-xl text-center lg:text-2xl xl:text-5xl mb-10">
              Register Page
            </h1>
            <div class="text-center mb-4 w-3/5">
              <img
                src="https://cdn.dribbble.com/users/79571/screenshots/5516891/workflow_4x.png"
                style="width:500px"
              >
            </div>
          </div>
        </div>
        <div class="w-2/5  h-12 row-left">
          <div class="text-singup mb-8">
            <h2 class="">
              Join us for free
            </h2>
          </div>
          <div class="form-signup-dig">
            <div class="w-full max-w-xs">
              <form
                @submit.prevent="registerHandler"
                class="max-w-md mb-4 form-input"
              >
                <div class="mb-4">
                  <label
                    class="block text-grey-darker text-sm font-bold mb-2"
                    for="username"
                  >
                    Username
                  </label>
                  <input
                    v-model="user.username"
                    class="shadow appearance-none border rounded w-full text-grey-darker leading-tight focus:outline-none focus:shadow-outline py-2 px-4"
                    id="username"
                    type="text"
                    placeholder="Username"
                  >
                </div>
                <div class="mb-4">
                  <label
                    class="block text-grey-darker text-sm font-bold mb-2"
                    for="password"
                  >
                    Email
                  </label>
                  <input
                    v-model="user.email"
                    class="shadow appearance-none border rounded h-12 w-full py-2 px-4 text-grey-darker mb-3 leading-tight focus:outline-none focus:shadow-outline"
                    id="password"
                    type="email"
                    placeholder="email"
                  >
                </div>
                <div class="mb-6">
                  <label
                    class="block text-grey-darker text-sm font-bold mb-2"
                    for="password"
                  >
                    Password
                  </label>
                  <input
                    v-model="user.password"
                    class="shadow appearance-none border rounded w-full h-12 py-2 px-4 text-grey-darker mb-3 leading-tight focus:outline-none focus:shadow-outline"
                    type="password"
                    placeholder="your password"
                  >
                </div>
                <div class="flex items-center justify-between">
                  <button
                    class="bg-blue hover:bg-blue-dark bg-blue-400 text-white font-bold w-full h-12 py-2 px-4  rounded focus:outline-none focus:shadow-outline"
                    type="submit"
                  >
                    Sign In
                  </button>
                </div>
              </form>

            </div>
          </div>
        </div>
      </div>

    </div>
  </div>
</template>

<script>
export default {
  name: "RegistrationPage",
  data() {
    return {
      user: {
        username: "",
        email: "",
        password: "",
      },
    };
  },
  methods: {
    async registerHandler() {
      try {
        await this.$store.dispatch("registerHandler", this.user);
        this.$router.push({ name: "login" });
      } catch (error) {
        console.log(error);
      }
    },
  },
};
</script>

<style>
</style>