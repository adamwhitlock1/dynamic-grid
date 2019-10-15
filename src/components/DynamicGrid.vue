<template>
  <div class="base-container">
    <div class="input-group">
      <label class="input-label" for="columns">Columns</label>
      <input class="input-text" type="number" name="columns" v-model.number="columns">
      
      <label class="input-label" for="elements">Elements</label>
      <input class="input-text" type="number" name="elements" v-model.number="elements">
    </div>

    <div class="grid-container" :style="{ 'grid-template-columns': `repeat(${columns}, 1fr)` }">
      <div
        class="grid-element"
        :style="{ 'background-color': `rgba(${randomBgColor()}, ${randomBgColor()}, ${randomBgColor()}, .7)` }"
        v-for="(el, index) in elements"
        :key="index"
      >
        <p class="element-text">{{ index + 1 }}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String
  },
  data() {
    return {
      columns: 4,
      elements: 20
    };
  },
  methods: {
    randomBgColor() {
      return Math.floor(Math.random() * 255 + 1);
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.grid-container {
  display: grid;
}

.grid-element {
  display: flex;
  width: 100%;
  height: 100px;
  align-items: center;
  text-align: center;
  /* background-image: url("https://wildcard.fun/r/600/200"); */
  background-position: center center;
  background-repeat: no-repeat;
  background-size: contain;
}

.element-text {
  align-self: center;
  color: white;
  background-color: rgba(0, 0, 0, 0.6);
  width: 20%;
  padding: 10px;
  border-radius: 150px;
  margin: 0 auto;
}

.input-group {
  margin: 30px;
}

.input-group * {
  font-size: 18px;
}
.input-group .input-label {
  padding: 10px;
}

.input-group .input-text {
  height: 24px;
  padding: 5px;
}
</style>
