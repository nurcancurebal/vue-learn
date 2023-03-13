<template>
  <div>
    <div>
      <h1>for döngüsü</h1>
      <p v-for="i in 4" v v-bind:key="i">{{ i }}</p>
      <p v-for="(item, index) in person" v-bind:key="index">
        name: {{ item.name }} age: {{ item.age }}
      </p>
    </div>

    <div>
      <h1>v-model</h1>

      <label>
        <input v-model.lazy="message" placeholder="edit me" />
        <textarea v-model.number.trim="area" />
        <input type="checkbox" v-model="checked" />

        <label>
          <select v-model="selected">
            <option disabled>select one</option>
            <option>A</option>
            <option>B</option>
            <option>C</option>
            <option>D</option>
          </select>
        </label>
      </label>

      <label>
        <select></select>
      </label>

      <p>{{ message }}</p>
      <p>{{ area }}</p>
      <p>{{ typeof area }}</p>
      <p>{{ checked }}</p>
      <p>{{ selected }}</p>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      person: [
        { name: "nurcan", age: "27" },
        { name: "erdinç", age: "30" },
        { name: "bal", age: "3" },
        { name: "ersel", age: "35" },
      ],
      message: "",
      area: "",
      checked: "",
      selected: null,
    };
  },

  methods: {},
};
</script>

<style>
</style>