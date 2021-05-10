<template>
  <v-app>
    <app-header></app-header>
    <v-content>
      <app-form></app-form>
    </v-content>
  </v-app>
</template>

<script>
import AppHeader from './components/AppHeader';
import AppForm from './components/AppForm';

export default {
  name: 'App',

  components: {
    'app-header': AppHeader,
    'app-form': AppForm,
  },

  data: () => ({
    //
  }),
};
</script>

<style>
.v-application {
  min-width: 360px;
}
</style>