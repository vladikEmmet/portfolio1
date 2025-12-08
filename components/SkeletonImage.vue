<template>
  <div class="wrapper" :style="{ aspectRatio: aspect }">

    <!-- Skeleton -->
    <div v-if="!loaded" class="skeleton"></div>

    <!-- Image -->
    <img
      ref="img"
      :src="src"
      :alt="alt"
      class="image"
      @load="onLoad"
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

  mounted() {
    const img = this.$refs.img;

    // Если изображение уже загружено (из кеша) → убрать skeleton
    if (img.complete) {
      this.loaded = true;
    }
  },

  methods: {
    onLoad() {
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

/* SKELETON */
.skeleton {
  position: absolute;
  inset: 0;
  background: linear-gradient(90deg, #333 0%, #444 50%, #333 100%);
  background-size: 200% 100%;
  animation: skeleton-loading 1.2s infinite;
  border-radius: 8px;
}

/* IMAGE */
.image {
  width: 100%;
  height: 100%;
  object-fit: contain;
  opacity: 0;
  transition: opacity 0.3s ease;
}

/* Плавное появление */
.image[src] {
  opacity: 1;
}

/* анимация скелетона */
@keyframes skeleton-loading {
  0% { background-position: 200% 0; }
  100% { background-position: -200% 0; }
}
</style>
