<template>
  <q-card class="qcard--border q-mt-md" :style="`width: ${width}`">
    <q-card-section class="qcard-title">
      {{ title }}
      <p v-if="subtitle">{{ subtitle }}</p>
    </q-card-section>
    <q-card-section>
      <slot name="content" />
    </q-card-section>
    <q-card-actions class="qcard--actions">
      <slot name="actions" />
    </q-card-actions>
  </q-card>
</template>

<script>
import { defineComponent } from 'vue';
export default defineComponent({
  name: 'GenericCard',
  props: {
    title: {
      type: String,
      required: false,
    },
    subtitle: {
      type: String,
      required: false,
    },
    width: {
      type: String,
      default: '100%',
    },
  },
});
</script>

<style>
.qcard--border {
  border-radius: 15px;
}
.qcard--actions {
  background: rgb(197, 197, 197);
}
.qcard-title {
  font-family: Helvetica;
  font-size: 18px;
  font-style: normal;
  font-weight: 400;
  line-height: 37px;
  letter-spacing: 0.01em;
  text-align: left;
  color: rgb(25, 25, 25);
  background: rgb(197, 197, 197);
}
</style>
