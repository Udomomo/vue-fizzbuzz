<template>
  <div class="panel" @click="clickAns">
      <div class="thumbnail">
        <img :src="srcPath" :alt="srcAlt">
      </div>
      <div>
        <p>{{ text }}</p>
      </div>
  </div>
</template>

<script>
export default {
  name: 'panel',
  props: ['text', 'srcPath', 'srcAlt'],
  methods: {
    clickAns: function(event) {
      this.$emit('select', this.text, event)
    }
  }
}
</script>

<style scoped>

.panel {
  display: inline-block;
  margin: 1%;
  width: 46%;
  border: solid;
  border-color: #83cd29;
  border-radius: 10px;
  text-align: center;
  transition: background-color 0.15s ease-in-out;
}

.panel:hover {
  border-color: #5f9ea0;
  cursor: pointer;
}

.panel * {
  pointer-events: none;
}

.thumbnail > img {
  margin-top: 20px;
  width: 40%;
}
</style>
