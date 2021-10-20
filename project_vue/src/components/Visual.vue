<template>
  <div id="visual">
    <img src="../assets/visual_1.png" alt="" />
    <div class="inner visual">
      <img src="../assets/visual_2-1.png" alt="" />
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
#visual {
  width: 100%;
  height: 300px;

  position: relative;
}
#visual img {
  width: inherit;
  height: inherit;
}
.visual {
  position: absolute;
  left: 50%;
  transform: translateX(-50%);

  top: 0%;
}
.visual img {
  width: 500px;
  height: 300px;
}
.inner {
  width: 1200px;
  margin: auto;
}
</style>
