<template>
  <q-page class="bg-grey-3 column">
    <q-list class="bp-white" separator bordered>
      <q-item v-for="(task, index) in tasks" :key="task.title" @click="task.done != task.done"
        :class="{ 'done bg-blue-1': task.done }" clickable v-ripple>
        <q-item-section avatar>
          <q-checkbox v-model="task.done" color="primary" />
        </q-item-section>
        <q-item-section>
          <q-item-label>{{ task.title }}</q-item-label>
        </q-item-section>
        <q-item-section v-if="task.done" side>
          <q-btn @click.stop="deleteTask(index)" flat round dense color="primary" icon="delete" />
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
  },

  methods: {
    deleteTask(index) {
      this.$q.dialog({
        title: 'Confirm',
        message: 'voulez-vous vraiment supprimer?',
        cancel: true,
        persistent: true
      }).onOk(() => {
        this.tasks.splice(index, 1)
        this.$q.notify('Ligne supprimé')

      })
    }
  }
})
</script>

<style lang="scss">
.done {
  q-item__label {
    text-decoration: line-through;
    color: #26A69A;
  }
}
</style>
