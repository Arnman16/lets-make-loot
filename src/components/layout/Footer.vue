<template>
  <v-footer padless class="footer">
    <v-card class="flex footer" flat tile>
      <div class="icon-links">
        <v-spacer />
        <v-btn
          v-for="(link, i) in links"
          :key="i"
          class="mx-4"
          dark
          icon
          :href="link.href"
          target="_blank"
        >
          <v-icon size="26px" :color="`${link.color} lighten-1`">
            {{ link.icon }}
          </v-icon>
        </v-btn>
        <v-spacer />
      </div>

      <v-card-text class="py-2 white--text text-center">
        {{ new Date().getFullYear() }} — <strong>Lets Make Loot</strong>
      </v-card-text>
    </v-card>
  </v-footer>
</template>
<script>
export default {
  name: "Footer",
  data: () => ({
    links: [
      {
        icon: "mdi-email",
        color: "white",
        href: "mailto:nick@letsmakeloot.com",
      },
      { icon: "mdi-youtube", color: "red", href: "http://youtube.com" },
      {
        icon: "mdi-twitter",
        color: "blue",
        href: "https://twitter.com/letsmakeloot",
      },
      {
        icon: "mdi-instagram",
        color: "purple",
        href: "https://www.instagram.com/letsmakeloot",
      },
      {
        icon: "mdi-reddit",
        color: "deep-orange",
        href: "https://reddit.com/r/letsmakeloot",
      },
    ],
  }),
};
</script>
<style scoped>
.icon-links {
  display: flex;
  margin: 6px;
}
.footer {
  background: linear-gradient(0deg, #181818 0px, #0000 60px) !important;
  opacity: 0.85;
}
</style>
