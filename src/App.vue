<template>
  <div id="app">
    <div>
      <p>按钮类型</p>
      <VButton @click="onClick">Basic Button</VButton>
      <v-button outline @click="onClick">Outline Button</v-button>
      <v-button clear @click="onClick">Clear Button</v-button>
      <v-button round @click="onClick">Round Button</v-button>
      <v-button block @click="onClick">Block Button</v-button>
      <v-button full @click="onClick">Full Button</v-button>
      <v-button disabled @click="onClick">Disabled Button</v-button>
    </div>

    <div>
      <p>按钮大小</p>
      <v-button title="small" @click="onClick" />
      <v-button small @click="onClick">Small Button</v-button>
      <v-button @click="onClick">Normal Button</v-button>
      <v-button large @click="onClick">Large Button</v-button>
    </div>

    <div>
      <p>按钮主题</p>
      <v-button @click="onClick">Primary Button</v-button>
      <v-button light @click="onClick">Light Button</v-button>
      <v-button success @click="onClick">Success Button</v-button>
      <v-button info @click="onClick">Info Button</v-button>
      <v-button warning @click="onClick">Warning Button</v-button>
      <v-button danger @click="onClick">Danger Button</v-button>
      <v-button dark @click="onClick">Dark Button</v-button>
    </div>
    <v-list :items="items"></v-list>
    <v-list-object :object="object" />
    <v-todo-list />
    <br />
    <v-form />

    <a v-bind:href="url" class="nav-link">
      <slot></slot>
    </a>

    <input v-focus />

    <div id="hook-arguments-example" v-demo:foo.a.b="message"></div>
  </div>
</template>


<script>
import VButton from "./components/Button";
import VList from "./components/List";
import VListObject from "./components/ListForObject";
import VTodoList from "./components/TodoList";
import VForm from "./components/FromDemo";

export default {
  name: "app",
  components: {
    VButton,
    VList,
    VListObject,
    VTodoList,
    VForm,
  },
  methods: {
    onClick: (title) => alert(title),
  },
  data() {
    return {
      items: [{ message: "Foo" }, { message: "Bar" }],
      object: {
        title: "How to do lists in Vue",
        author: "Jane Doe",
        publishedAt: "2016-04-10",
      },
      message: "hello!",
    };
  },
  directives: {
    focus: {
      // 指令的定义
      inserted: function (el) {
        el.focus();
      },
    },

    demo: {
      bind: function (el, binding, vnode) {
        var s = JSON.stringify;
        el.innerHTML =
          "name: " +
          s(binding.name) +
          "<br>" +
          "value: " +
          s(binding.value) +
          "<br>" +
          "expression: " +
          s(binding.expression) +
          "<br>" +
          "argument: " +
          s(binding.arg) +
          "<br>" +
          "modifiers: " +
          s(binding.modifiers) +
          "<br>" +
          "vnode keys: " +
          Object.keys(vnode).join(", ");
      },
    },
  },
};
</script>




<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
