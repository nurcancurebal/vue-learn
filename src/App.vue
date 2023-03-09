<template>
  <div id="app">
    <h1>App Area</h1>
    <Nav />

    <div>
      <div v-if="tryOne() === 1">This is 1</div>
      <div v-else-if="tryOne() === 2">This is 2</div>
      <div v-else-if="tryTwo === 3">This is 3</div>
      <div v-else-if="tryThree">This is 4</div>
      <div v-else>This is 5</div>
    </div>

    <div>
      <div v-if="Math.random() > 0.5">This is Bigger</div>
      <div v-else>This is smaller</div>
    </div>

    <div>
      <div v-if="tryThree">
        This is Bigger
        <label>
          <input key="1" placeholder="input1" />
        </label>
      </div>

      <div v-else>
        This is smaller
        <label>
          <input key="2" placeholder="input2" />
        </label>
      </div>
    </div>

    <div>
      <div v-if="tryThree">
        This is Computed
        <label>
          <input key="1" placeholder="input1" />
        </label>
      </div>

      <div v-show="value">
        This is Show
        <label>
          <input key="2" placeholder="input2" />
        </label>
      </div>
    </div>

    <Footer />

    <For />
  </div>
</template>

<script>
import Nav from "./components/Nav.vue";
import Footer from "./components/Footer.vue";
import For from "./components/For.vue";

export default {
  data() {
    return {
      value: true,
    };
  },

  name: "App",
  components: {
    Nav,
    Footer,
    For,
  },

  methods: {
    tryOne() {
      return 3;
    },
  },

  computed: {
    tryTwo() {
      return 4;
    },

    tryThree() {
      const a = Math.random() > 0.5;
      console.log(a);
      return a;
    },
  },
};
</script>