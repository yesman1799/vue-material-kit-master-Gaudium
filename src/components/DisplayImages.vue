<template>
  <div v-if="imagesLoaded" class="image-container">
    <img
      v-for="(image, index) in images"
      :key="index"
      :src="image"
      :alt="`Image ${index + 1}`"
      class="img-fluid rounded"
      @error="handleImageError"
    />
  </div>
</template>

<script>
import army1 from "@/assets/img/armys.jpg";
import army2 from "@/assets/img/army.jpg";
import army3 from "@/assets/img/armyc.jpg";

export default {
  data() {
    return {
      images: [army1, army2, army3],
      imagesLoaded: false,
    };
  },
  mounted() {
    this.imagesLoaded = true; // Mark images as loaded for simplicity
  },
  methods: {
    handleImageError(error) {
      console.error("Error loading image:", error.target.src);
    },
  },
};
</script>

<style scoped>
.image-container {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 10px; /* Adjust the gap as needed */
  padding: 20px;
}

.img-fluid {
  max-width: 20%;
  height: auto;
  border-radius: 20px;
  border: 5px solid #54ad58;
}
</style>
