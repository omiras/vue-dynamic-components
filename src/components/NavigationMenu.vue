<template>
  <ul>
    <li>
      <navigation-item @click="clickedItem"
        imageURL="/cats/svg/006-box.svg"
        id="messages"
      ></navigation-item>
    </li>
    <li>
      <navigation-item @click="clickedItem"
        imageURL="/cats/svg/043-love.svg"
        id="favorites"
      ></navigation-item>
    </li>
  </ul>
</template>

<script>
import NavigationItem from "./NavigationItem.vue";

export default {
  components: { NavigationItem },
  methods: {
    clickedItem(event) {
      this.$emit('selectedItem', event.target.id)
    }
  }
};
</script>

<style scoped>
ul {
  list-style-type: none;
  margin: 0;
  padding: 0;
  overflow: hidden;
  background-color: #333333;
  display: flex;
  flex-direction: row;
  justify-content: space-evenly;
}

li {
  float: left;
}

li a {
  display: block;
  color: white;
  text-align: center;
  padding: 16px;
  text-decoration: none;
}

li a:hover {
  background-color: #1b2b1c;
}
</style>