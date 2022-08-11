<script setup>
import { reactive } from "vue";

import cnf from "../cnf.json";

const props = defineProps({
  trackingCode: { type: Number, default: cnf.trackingCode },
  clientId: { type: Number, default: cnf.clientId },
  host: { type: String, default: cnf.host },
  addComponent: { type: Function, default: () => {} },
  clearComponents: { type: Function, default: () => {} },
  promise: { type: Function, default: () => {} },
});

let script = reactive({
  included: false,
  gtm: false,
});

const includeScript = (url, id = null) => {
  const script = document.createElement("script");
  script.src = url;
  script.async = true;
  if (id) {
    script.id = id;
  }
  document.body.appendChild(script);
  return () => {
    document.body.removeChild(script);
  };
};

const configure = () => {
  window.AvanserOptions = {
    clientId: props.clientId,
    trackingCode: props.trackingCode,
  };
  includeScript(`https://${props.host}/aa.js`, "AVANSERjs");
  script.included = true;
};

const gtm = () => {
  if (script.gtm) {
    return;
  }
  window.dataLayer = window.dataLayer || [];
  function gtag() {
    window.dataLayer.push(arguments);
  }
  gtag("js", new Date());
  gtag("config", "G-WC6MG8RL1R");
  script.gtm = true;
};

gtm();
</script>

<template>
  <div class="App-Configuration" v-if="script.included === false">
    <table className="Configuration-View">
      <tbody>
        <tr>
          <th>Client ID</th>
          <td>
            <!-- eslint-disable-next-line prettier/prettier -->
            <input name="clientId" type="number" min="4" max="4" v-bind:value="clientId" />
          </td>
        </tr>
        <tr>
          <th>Tracking Code</th>
          <td>
            <!-- eslint-disable-next-line prettier/prettier -->
            <input name="trackingCode" type="number" min="1" max="4" v-bind:value="trackingCode" />
          </td>
        </tr>
        <tr>
          <th></th>
          <td><button @click="configure">START TEST</button></td>
        </tr>
      </tbody>
    </table>
  </div>
  <div v-else>
    <div className="App-Buttons">
      &nbsp;&nbsp;
      <button @click="() => addComponent('button')">Add Button</button>
      &nbsp;&nbsp;
      <button @click="() => addComponent('header')">Add Header</button>
      &nbsp;&nbsp;
      <button @click="() => addComponent('span')">Add Span</button>
      &nbsp;&nbsp;
      <button @click="promise">Use Promise</button>
      &nbsp;&nbsp;
      <button @click="clearComponents">Clear</button>
    </div>
  </div>
</template>
