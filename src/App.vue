<template>
  <v-app>
    <Navbar />
    <v-main>
      <v-container fluid fill-height justify-center>
        <v-slide-x-transition mode="out-in">
          <router-view />
        </v-slide-x-transition>
      </v-container>
    </v-main>
    <Footer />
  </v-app>
</template>

<script>
import Navbar from "@/components/layout/Navbar";
import Footer from "@/components/layout/Footer";
export default {
  name: "App",
  components: { Navbar, Footer },

  data: () => ({
    //
  }),
};
</script>
<style lang="css">
/* width */
::-webkit-scrollbar {
  width: 10px;
}

/* Track */
::-webkit-scrollbar-track {
  background: #121212;
}

/* Handle */
::-webkit-scrollbar-thumb {
  background: #333;
}

/* Handle on hover */
::-webkit-scrollbar-thumb:hover {
  background: #555;
}
</style>
