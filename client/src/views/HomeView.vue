<template>
  <div class="home">
    <div class="container">
      <div class="row">
        <div class="col"></div>
        <div class="col-8">
          <div class="jumbotron" style="background-color: transparent">
            <h1 class="display-6">Welcome to DentistFinder</h1>
            <img src="@/assets/dentist_logo.png" class="rounded-circle centered" style="max-width: 150px; margin: 20px 0px 20px 0px; box-shadow: 0px 0px 68px -7px rgba(0, 0, 0, 0.61)" alt="Avatar" />
            <p class="lead">
              Lorem ipsum dolor sit amet consectetur adipisicing elit. Consectetur blanditiis nihil iure error rem? Voluptatem dolor nemo quasi sunt, voluptates exercitationem? Cumque nobis sed voluptas dolor et excepturi aliquam consequatur!
            </p>
            <hr class="my-4" />
            <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Nemo quisquam dolorum nostrum. Voluptate commodi magnam non blanditiis quod quisquam laboriosam, sequi eum unde perspiciatis fugiat quaerat neque consequuntur et sit!</p>
            <p class="lead">
              <button class="btn btn-primary btn-lg" @click.prevent="navigateFindDentist()">Find dentist!</button>
            </p>
          </div>
        </div>
        <div class="col"></div>
      </div>
    </div>
  </div>
</template>

<script>
import router from "@/router";
import InternalStorage from "@/InternalStorage";

export default {
  name: "HomeView",
  components: {},

  data() {
    return {
      InternalStorage,
    };
  },

  async created() {},

  methods: {
    navigateFindDentist() {
      if (InternalStorage.userAuth) {
        router.push("/findDentist");
      } else {
        router.push("/login");
      }
    },
  },
};
</script>

<style>
#home {
  background-image: linear-gradient(#2c3e50, #7490ab);
  background-repeat: no-repeat;
  background-size: auto;
  background-position: center;
  height: 100%;
  max-height: 100%;
}
</style>
