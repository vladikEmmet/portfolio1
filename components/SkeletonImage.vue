<template>
  <div class="wrapper" :style="{ aspectRatio: aspect }">

    <div v-if="!loaded" class="skeleton"></div>

    <img
      v-show="loaded"
      :src="src"
      :alt="alt"
      @load="handleLoad"
      class="image"
      draggable="false"
    />
  </div>
</template>

<script>
export default {
  props: {
    src: { type: String, required: true },
    alt: { type: String, default: "" },
    aspect: { type: String, default: "16/9" }
  },
  data() {
    return {
      loaded: false
    };
  },
  methods: {
    handleLoad() {
      this.loaded = true;
    }
  }
};
</script>

<style scoped>
.wrapper {
  width: 100%;
  position: relative;
  overflow: hidden;
  user-select: none;
}

.skeleton {
  width: 100%;
  height: 100%;
  background: linear-gradient(90deg, #333 0%, #444 50%, #333 100%);
  background-size: 200% 100%;
  animation: skeleton-loading 1.2s infinite;
  border-radius: 6px;
}

/* image */
.image {
  width: 100%;
  height: 100%;
  object-fit: contain;
  transition: opacity 0.3s ease;
}

@keyframes skeleton-loading {
  0% { background-position: 200% 0; }
  100% { background-position: -200% 0; }
}
</style>
