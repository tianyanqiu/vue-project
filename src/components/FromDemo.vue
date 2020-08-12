<template>
  <div>
    <input type="checkbox" id="jack" value="Jack" v-model="checkedNames" />
    <label for="jack">Jack</label>
    <input type="checkbox" id="john" value="John" v-model="checkedNames" />
    <label for="john">John</label>
    <input type="checkbox" id="mike" value="Mike" v-model="checkedNames" />
    <label for="mike">Mike</label>
    <br />
    <span>Checked names: {{ checkedNames }}</span>

    <div id="example-5">
      <select v-model="selected">
        <option disabled value>请选择</option>
        <option>A</option>
        <option>B</option>
        <option>C</option>
      </select>
      <span>Selected: {{ selected }}</span>
    </div>

    <div id="example-6">
      <select v-model="selectedM" multiple style="width: 50px;">
        <option>A</option>
        <option>B</option>
        <option>C</option>
      </select>
      <br />
      <span>Selected: {{ selectedM }}</span>
    </div>

    <div>
      <select v-model="selectedV">
        <option
          v-for="option in options"
          v-bind:value="option.value"
          :key="option.value"
        >{{ option.text }}</option>
      </select>
      <span>Selected: {{ selectedV }}</span>
    </div>

    <input v-model.lazy="message" placeholder="edit me" />
    <p>Message is: {{ message }}</p>
  </div>
</template>

<script>
export default {
  name: "v-form",
  data() {
    return {
      checkedNames: [],
      selected: "",
      selectedM: [],
      selectedV: "A",
      options: [
        { text: "One", value: "A" },
        { text: "Two", value: "B" },
        { text: "Three", value: "C" },
      ],
      message: "",
    };
  },
};
</script>