<template>
  <q-page class="bg-grey-3 column">
    <q-list class="bp-white">
      <q-item v-ripple>
        <q-item-section avatar>
          <q-checkbox v-model="color" color="primary" />
        </q-item-section>
        <q-item-section>
          <q-item-label>Teal</q-item-label>
        </q-item-section>
      </q-item>
    </q-list>
  </q-page>
</template>

<script>
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'A_Faire',

  data() {
    return {
      tasks: [
        {
          title: 'Choix 1',
          done: false
        },
        {
          title: 'Choix 2',
          done: false
        },
        {
          title: 'Choix 3',
          done: false
        }
      ]

    }
  }
})
</script>
