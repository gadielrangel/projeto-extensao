<template>
  <div class="q-pa-md row items-start q-gutter-md" style="width: 400px;">
    <q-card class="my-card" flat bordered>
      <slot name="media">
        <q-img :src="props.image" />
      </slot>

      <q-card-section>
        <div class="text-overline text-orange-9">{{ props.overline }}</div>
        <div class="text-h5 q-mt-sm q-mb-xs">{{ props.title }}</div>
        <div class="text-caption text-grey">

          <slot></slot>
        </div>
      </q-card-section>

      <q-card-actions>
        <q-btn flat color="primary" label="Compartilhar" />
        <q-btn flat color="secondary" label="Doar" />

        <q-space />

        <q-btn color="grey" round flat dense :icon="expanded ? 'keyboard_arrow_up' : 'keyboard_arrow_down'"
          @click="expanded = !expanded" />
      </q-card-actions>

      <q-slide-transition>
        <div v-show="expanded">
          <q-separator />

          <q-card-section class="text-subtitle2">
            <slot name="expand-content"></slot>
          </q-card-section>
        </div>
      </q-slide-transition>
    </q-card>
  </div>
</template>


<script setup lang="ts">
import { ref } from "vue"

const expanded = ref(false)

const props = defineProps({
  image: { type: String, default: () => "https://cdn.quasar.dev/img/parallax2.jpg" },
  overline: { type: String, default: () => "overline" },
  title: { type: String, default: () => "title" },
})
</script>

<style scoped></style>
