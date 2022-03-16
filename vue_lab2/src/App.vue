<template>
  <div id="app">
    <Navbar />
    <p>The result of 2 + 2 is: {{ mathResult }}</p>
    <p v-if="isShown">The result of 2 * 3 is: {{ printFunction() }}</p>
    <button @click="isShown = true">Print 2*3</button>
    <br>
    <button
      v-for="verduras in groceries"
      :key="verduras.id"
      @click="showGroceries(element)"
    >
      {{ verduras.name }}
    </button>
    <div class="card" :style="{ background: bcgColor }" >Este card cambia de color</div>
    <Footer />
  </div>
</template>

<script>
import Navbar from "./components/Navbar.vue";
import Footer from "./components/Footer.vue";
export default {
  data() {
    return {
      mathResult: 2 + 3,
      isShown: false,
      bcgColor: "#439A86",
      groceries: [
        {
          id: 1,
          name: "Tomate",
          color: "red",
        },
        {
          id: 2,
          name: "Lechuga",
          color: "green",
        },
        {
          id: 3,
          name: "Cebolla",
          color: "purple",   
        },
      ],
    };
  },
  components: {
    Navbar,
    Footer,
  },
  methods: {
    printFunction() {
      return 2 * 3;
    },
    showGroceries(element) {
      this.bcgColor = element.color;
    },
  },
};
</script>

<style>
#app {
  text-align: center;
  color: #2c3e50;
}

.card {
  padding: 10px;
  background-color: royalblue;
}
</style>
