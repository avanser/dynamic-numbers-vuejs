<script setup>
import { reactive } from "vue";
import NumberItem from "./components/NumberItem.vue";
import ConfigurationView from "./components/ConfigurationView.vue";

const components = reactive([]);

const addComponent = (type) => {
  components.push(type);
  console.log("addComponent", type, components);
};

const clearComponents = () => {
  components.splice(0, components.length);
  console.log("clearComponents", components);
};

function promise() {
  window["$AA"].getNumber("0401020304").then((numberObject) => {
    let text =
      promise.toString() +
      "\n\nPromise Response:\n" +
      JSON.stringify(numberObject, null, " ");
    addComponent(text);
  });
}
</script>

<template>
  <div className="App">
    <header className="App-header">
      <img src="./assets/logo.svg" className="App-logo" alt="logo" />
      <p>
        Vue.JS<br />
        AVANSER Dynamic Numbers
      </p>
      <pre>0401020304</pre>
      <ConfigurationView
        v-bind:addComponent="addComponent"
        v-bind:clearComponents="clearComponents"
        v-bind:promise="promise"
      />
      <hr className="App-Element" />
    </header>
    <main>
      <div className="App-Numbers">
        <div
          className="App-Element"
          v-for="component of components"
          :key="component"
        >
          <NumberItem v-bind:type="component" />
        </div>
      </div>
    </main>
  </div>
</template>
