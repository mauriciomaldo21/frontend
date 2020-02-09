<template>
  <v-carousel cycle height="500" hide-delimiter-background show-arrows-on-hover>
    <v-carousel-item v-for="(slide, i) in photos" :key="i">
      <v-sheet :color="secundary" height="100%">
        <v-row class="fill-height" align="center" justify="center">
          <cld-image v-bind:publicId="slide.public_id">
            <cld-transformation quality="30" fetchFormat="auto" width="700" crop="scale" />
          </cld-image>
          <v-btn class="mx-2"  @click="ver(slide.imageURL)">
            <v-icon dark>mdi-eye</v-icon>
          </v-btn>
        </v-row>
      </v-sheet>
    </v-carousel-item>
  </v-carousel>
</template> 

<script>
export default {
  data() {
    return {
      photos: [],
      overlay: false,
      dialog: false,
      colors: ["secundary"]
    };
  },
  created() {
    this.listPhotos();
  },
  methods: {
    ver(url) {
      var a = document.createElement("a");
      a.target = "_blank";
      a.href = url;
      a.click();
    },
    listPhotos() {
      this.axios
        .get("images")
        .then(response => {
          this.photos = response.data;
        })
        .catch(e => {
          console.log("error" + e);
        });
    }
  }
};
</script>
