<template>
  <section class="gallery">
    <div class="row">
      <div class="col-lg-12">
        <div class="card">
          <div class="card-body">
            <h4 class="card-title">Gallery</h4>
            <gallery :images="images" :index="index" @close="index = null"></gallery>
            <div
              class="image"
              v-for="(image, imageIndex) in images"
              :key="imageIndex"
              @click="index = imageIndex"
              :style="{ backgroundImage: 'url(' + image + ')', width: '24%', height: '100px' }"
            ></div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
  import VueGallery from 'vue-gallery';
  export default {
      data: function () {
        return {
          images: [
            require('../../assets/images/samples/1280x768/1.jpg'),
            require('../../assets/images/samples/1280x768/2.jpg'),
            require('../../assets/images/samples/1280x768/3.jpg'),
            require('../../assets/images/samples/1280x768/4.jpg'),
            require('../../assets/images/samples/1280x768/5.jpg'),
            require('../../assets/images/samples/1280x768/6.jpg'),
            require('../../assets/images/samples/1280x768/7.jpg'),
            require('../../assets/images/samples/1280x768/8.jpg'),
          ],
          index: null
        };
      },
  
      components: {
        'gallery': VueGallery
      },
    }
</script>
<style scoped>
  .image {
    float: left;
    background-size: cover;
    background-repeat: no-repeat;
    background-position: center center;
    border: 1px solid #ebebeb;
    margin: 5px;
  }
</style> 