<template>
  <div class="black-bg">
    <div class="white-bg">
      <h4>Details</h4>
      <span
        >Lorem ipsum dolor sit amet consectetur adipisicing elit. Facilis,
        eveniet amet? Commodi laudantium nulla accusantium ducimus reiciendis
        voluptates esse omnis ratione architecto molestias tempore fuga,
        accusamus velit eligendi quia id.</span
      >
    </div>
  </div>

  <div class="menu">
    <a v-for="(navMenu, i) in menu" :key="i">{{ navMenu }}</a>
  </div>

  <div class="products" v-for="(product, i) in products" :key="i">
    <img :src="images[i]" class="room-img" />
    <h4>{{ products[i] }}</h4>
    <p>{{ prices[i] }} dollars</p>
    <button @click="increase(i)">Report</button>
    <span>Report Count: {{ reportCount[i] }}</span>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      images: [
        require("./assets/room0.jpg"),
        require("./assets/room1.jpg"),
        require("./assets/room2.jpg"),
      ],
      reportCount: Array(3).fill(0),
      menu: ["Home", "Products", "About"],
      products: ["Toronto", "Richmond Hill", "Vaughan Mills"],
      prices: [60, 70, 100],
    };
  },
  methods: {
    increase(index) {
      this.reportCount[index]++;
    },
  },
  components: {},
};
</script>

<style>
body {
  margin: 0;
}

div {
  box-sizing: border-box;
}

.black-bg {
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
  position: fixed;
  padding: 20px;
}

.white-bg {
  width: 100%;
  background: white;
  border-radius: 8px;
  padding: 20px;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.menu {
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}

.menu a {
  color: white;
  padding: 10px;
}

.room-img {
  width: 100%;
  margin-top: 40px;
}
</style>
