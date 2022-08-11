<script setup>
import { computed } from "vue";

const props = defineProps({
  trackingCode: { type: Number, default: 51 },
  isDefault: { type: Boolean, default: false },
  text: { type: String, default: "0401020304" },
  number: { type: String, default: "0401020304" },
  type: { type: String, default: "span" },
});

const link = computed(() => `tel://${props.number}`);
</script>

<template>
  <div v-if="type === 'header'">
    <h3>
      Call us: <a v-bind:href="link">{{ text }}</a>
    </h3>
  </div>
  <div v-else-if="type === 'button'">
    <div>
      <button>Call us: {{ text }}</button>
    </div>
  </div>
  <div v-else-if="type === 'span'">
    <span>
      Our call center is always available to take your call, contact us at
      <a v-bind:href="link">
        {{ text }}
      </a>
      !
    </span>
  </div>
  <div v-else>
    <pre>{{ type }}</pre>
  </div>
</template>
