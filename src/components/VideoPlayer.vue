<template>
  <div id=video class="video">
    <video
      id='video'
      width='500'
      height='400'
      poster='../assets/big_buck_bunny.jpeg'
      src='http://vpe-static.bamgrid.com/sample-files/take-home-exam/sample-mp4-file.mp4'
      controls
    />
  </div>
</template>

<script>
export default {
  name: 'VideoPlayer',
  props: {
    msg: String
  }
}
</script>

<style>
  .videoContainer {
    display: grid;
    grid-template-rows: repeat(2, 1fr);
  }

  video:focus {
    outline: none;
  }
</style>