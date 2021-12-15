<template>
  <v-app-bar
    :extension-height="navHeight"
    dense
    hide-on-scroll
    flat
    class="navbar"
    ><v-spacer />
    <v-btn
      href="https://www.youtube.com/watch?v=dQw4w9WgXcQ"
      target="_blank"
      fab
      text
      class="search"
    >
      <v-icon color="white">mdi-magnify</v-icon>
    </v-btn>
    <template v-slot:extension>
      <v-col no-gutters>
        <v-row class="justify-center">
          <router-link class="d-flex align-center" to="/">
            <v-img
              alt="LML Name"
              class="shrink title"
              contain
              :width="titleWidth"
              max-height="280"
              :src="logo"
            />
          </router-link>
        </v-row>
        <v-row no-gutters class="justify-center">
          <v-btn small to="/stuff" text>
            <span>Cool Stuff</span>
            <!-- <v-icon color="blue">mdi-emoticon-cool-outline</v-icon> --> </v-btn
          ><span style="color: #0099ff">|</span>
          <v-btn small to="/progress" text>
            <span>Progress</span>
            <!-- <v-icon color="blue">mdi-emoticon-cool-outline</v-icon> --> </v-btn
          ><span style="color: #0099ff">|</span>
          <v-btn
            href="https://www.youtube.com/watch?v=dQw4w9WgXcQ"
            target="_blank"
            text
            small
          >
            <span>Latest Video</span>
            <!-- <v-icon color="red">mdi-youtube</v-icon> -->
          </v-btn>
        </v-row>
      </v-col>
    </template>
  </v-app-bar>
</template>

<script>
import LML_titleDark from "@/assets/LML_titleDark.svg";
import icon from "@/assets/icon.svg";
export default {
  name: "Navbar",
  computed: {
    titleWidth() {
      switch (this.$vuetify.breakpoint.name) {
        case "xs":
          return 300;
        case "sm":
          return 350;
        case "md":
          return 400;
        case "lg":
          return 500;
        case "xl":
          return 600;
        default:
          return 400;
      }
    },
    navHeight() {
      switch (this.$vuetify.breakpoint.name) {
        case "xs":
          return 250;
        case "sm":
          return 250;
        case "md":
          return 250;
        case "lg":
          return 280;
        case "xl":
          return 300;
        default:
          return 200;
      }
    },
  },
  data() {
    return {
      logo: LML_titleDark,
      icon,
    };
  },
};
</script>

<style>
.navbar {
  background: linear-gradient(#1b1b1b 0px, #0000 60px) !important;
}
.title {
  opacity: 0.95;
  filter: drop-shadow(-2px 2px 0.3px #0099ff);
}
.title:hover {
  opacity: 1;
  background: rgba(255, 255, 255, 0.002);
  border-radius: 30px;
}
.logo {
  filter: drop-shadow(-2px 2px 1px black) blur(0.3px);
}
.search {
  opacity: 0.6;
  position: absolute;
  top: 0;
  right: 0;
  margin-top: 16px;
}
</style>
