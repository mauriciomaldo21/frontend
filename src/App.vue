<template>
  <v-app>
    <v-container>
      <HelloWorld />
    </v-container>
    <v-card height="80">
      <v-footer absolute class="font-weight-medium">
        <v-col class="text-center" cols="12">
          {{ new Date().getFullYear() }} —
          <strong>
            <span class="mr-2">Mauricio Maldonado</span>
            <v-icon>mdi-heart</v-icon>
          </strong>
        </v-col>
      </v-footer>
    </v-card>
  </v-app>
</template>

<script>
import HelloWorld from "./components/HelloWorld";

export default {
  name: "App",

  components: {
    HelloWorld
  },

  data: () => ({
    //
  })
};
</script>
