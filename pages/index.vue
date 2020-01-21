<template>
  <div class="container p-5">
    <div class="row">
      <div class="col-md-12 text-center">
        <b-img
          :src="selectedImage"
          fluid
          rounded
          alt="Responsive image"
        />
      </div>
    </div>
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
  </div>
</template>

<script>
export default {
  data(){
    return {
      images: [
        'img/pano 1.jpeg',
        'img/pano 2.jpeg',
        'img/pano 3.jpeg',
      ],
      selectedImage: 'img/pano 1.jpeg'
    }
  },
  methods: {
    selectImage(image){
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
</style>
