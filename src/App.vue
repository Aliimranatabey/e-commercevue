<template>
  <v-app>
    <NavigationDrawers />
    <DatatableVuetify />
  </v-app>
</template>

<script>
import DatatableVuetify from "./components/Datatable.vue";
import NavigationDrawers from "./components/NavigationDrawers";
export default {
  name: 'App',

  components: {
    DatatableVuetify,
    NavigationDrawers
  },

  data: () => {
    return {};
  },
};
</script>
