<template>
  <div>
    <h3 class='title'>{{ heading }}</h3>
    <ul>
      <li v-for="title in info" :key="title">
        {{ title.title }}
        <button v-on:click.self="changeVideo(title.url)">Change Video</button>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'TestList',
  props: {
    heading: String,
    info: Object
  },
  computed: {},
  methods: {
    changeVideo: function() {
      alert('video changed');
    }
  }
}
</script>

<style >
  .title {
    text-align: left;
    margin-left: 40px;
  }

  ul {
    list-style-type: none;
    display: block;
  }

  ul li {
    height: 40px;
    position: relative;
    border-bottom: 2px solid steelblue;
    padding-top: 20px;
    color: #373535;
    text-align: left;
  }

  button {
  background-color: #a184ad;
  width: 100px;
  height: 2rem;
  position: absolute;
  right: -10px;
  margin-top: -7px;
  color: #fff;
  font-weight: bold;
  border-radius: 12px;
  border: none;
}

  button:visited {
    background-color: #3cb371;
  }

  button:focus {
    outline: none;
  }

  button:active {
    background-color:green;
    border-radius: 12px;
    border: none;
  }
</style>