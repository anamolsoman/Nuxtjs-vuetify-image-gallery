<template>
  <v-row>
    <v-col>
      <v-card>
        <v-container fluid>
          <v-row cols="12" sm="9" offset-sm="1">
            <v-col v-for="(image, index) in images" :key="index" class="d-flex child-flex" cols="4">
              <v-card flat tile class="d-flex">
                <v-img
                  :src="image.imgSrc"
                  @click.stop=";(dialog = true), (id = index), (imgSrc = image.imgSrc)"
                  aspect-ratio="1"
                  class="grey lighten-2"
                >
                  <template v-slot:placeholder>
                    <v-row class="fill-height ma-0" align="center" justify="center">
                      <v-progress-circular indeterminate color="grey lighten-5"></v-progress-circular>
                    </v-row>
                  </template>
                </v-img>
              </v-card>
            </v-col>
            <v-dialog v-model="dialog" max-width="720">
              <v-card>
                <v-img :src="imgSrc" max-width="720" height="auto"></v-img>
                <v-card-actions>
                  <v-spacer></v-spacer>

                  <v-btn @click="dialog = false" color="red darken-1" text>
                    Close
                  </v-btn>
                </v-card-actions>
              </v-card>
            </v-dialog>
          </v-row>
        </v-container>
      </v-card>
    </v-col>
  </v-row>
</template>
<script>
export default {
  data() {
    return {
      dialog: false,
      id: '',
      imgSrc: require('~/static/noimage.png'),
      images: [
        { id: 1, imgSrc: require('assets/img/certificates/1.png') },
        { id: 2, imgSrc: require('assets/img/certificates/2.jpg') },
        { id: 3, imgSrc: require('assets/img/certificates/3.jpg') },
        { id: 4, imgSrc: require('assets/img/certificates/4.jpg') },
        { id: 5, imgSrc: require('assets/img/certificates/5.jpg') },
        { id: 5, imgSrc: require('assets/img/certificates/6.jpg') }
      ]
    }
  }
}
</script>
