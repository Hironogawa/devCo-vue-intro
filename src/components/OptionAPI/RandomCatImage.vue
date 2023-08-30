<script>
export default {
  props: {
    msg: {
      type: String,
      required: true,
    },
  },
  methods: {
    getCat() {
      document.getElementById("cat").src = "https://cataas.com/cat/gif";
    },
  },
  mounted() {
    this.getCat();
  },
};
</script>

<template>
  <div class="media-container">
    <img src="" id="cat" />
  </div>
</template>

<style scoped>
.media-container {
  height: fit-content;
}
#cat {
  width: 100%;
  height: 100%;
}
</style>
