<template>
  <div>
    <div>
      <h3>for döngüsü</h3>
      <p v-for="i in 4" v v-bind:key="'for1' + i">{{ i }}</p>
      <p v-for="(item, index) in person" v-bind:key="'for2' + index">
        name: {{ item.name }} age: {{ item.age }}
      </p>
    </div>

    <div>
      <h3>v-model</h3>

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
        <select v-model="selectedTwo">
          <option
            v-for="(item, index) in items"
            v-bind:value="item.value"
            v-bind:key="index"
          >
            {{ item.option }}
          </option>
        </select>
      </label>

      <div>
        <input type="radio" value="1" id="1" v-model="radio" />
        <label for="1">1</label>
        <input type="radio" value="2" id="2" v-model="radio" />
        <label for="2">2</label>
        <input type="radio" value="3" id="3" v-model="radio" />
        <label for="3">3</label>
      </div>

      <p>{{ message }}</p>
      <p>{{ area }}</p>
      <p>{{ typeof area }}</p>
      <p>{{ checked }}</p>
      <p>{{ selected }}</p>
      <p>{{ selectedTwo }}</p>
      <p>{{ radio }}</p>
    </div>

    <div>
      <h3>v-once</h3>
      <button v-once v-on:click="changevalue">{{ buttonvalue }}</button>
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
      selectedTwo: null,
      items: [
        { option: "a", value: "one" },
        { option: "b", value: "two" },
        { option: "c", value: "three" },
      ],
      radio: null,
      buttonvalue: true,
    };
  },
  methods: {
    changevalue() {
      this.buttonvalue = !this.buttonvalue;
      console.log(this.buttonvalue);
    },
  },
};
</script>

<style>
</style>