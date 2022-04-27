<template>
  <v-app>
    <!-- <v-main>
      <router-view />
    </v-main> -->
    <search-dropdown/>
  </v-app>
</template>

<script>
import SearchDropdown from './components/SearchDropdown.vue';
export default {
  components: { SearchDropdown },
  name: "App",

  data: () => ({
    //
  }),
};
</script>
