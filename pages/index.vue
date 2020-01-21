<template>
  <div class="container p-5">
    <div class="row mb-3">
      <div class="col-md-12 text-center">
        <!-- <b-img
          :src="selectedImage"
          fluid
          rounded
          alt="Responsive image"
        /> -->
        <VuePannellum
          :src="selectedImage"
          showZoom="true"
          showFullscreen="true"
          hfov="200"
          autoRotate="-2"
          vaov="0"
        ></VuePannellum>
      </div>
    </div>
    <h5>Panorama Photos</h5>
    <small>photos taken by Iphone X with pano</small>
    <div class="row text-center mt-3">
      <div class="col-md-4 my-2" v-for="image in images" :key="image">
        <b-img
          thumbnail
          fluid
          :src="image"
          alt="Image thumbnail"
          @click="selectImage(image)"
        ></b-img>
      </div>
    </div>
    <h5>360 Photos</h5>
    <small>photos taken from <a href="http://Pixelid.com">Pixelid.com</a></small>
    <div class="row text-center mt-3">
      <div class="col-md-4 my-2" v-for="image in images360" :key="image">
        <b-img
          thumbnail
          fluid
          :src="image"
          alt="Image thumbnail"
          @click="selectImage(image)"
        ></b-img>
      </div>
    </div>
  </div>
</template>

<script>
import VuePannellum from 'vue-pannellum'
export default {
  components: { VuePannellum },
  data() {
    return {
      images: ['/img/pano 1.jpg', '/img/pano 2.jpg', '/img/pano 3.jpg'],
      images360: [
        '/img/360-1.jpg',
        '/img/360-2.jpg',
        '/img/360-3.jpg',
        '/img/360-4.jpg',
        '/img/360-5.jpg',
        '/img/360-6.jpg'
      ],
      selectedImage: '/img/pano 1.jpg'
    }
  },
  methods: {
    selectImage(image) {
      this.selectedImage = image
    }
  }
}
</script>

<style>
.img-fluid {
  max-height: 400px;
}
body {
  background: #e1f5fe;
}
.vue-pannellum {
  height: 400px;
}
.img-thumbnail {
  cursor: pointer;
}
</style>
