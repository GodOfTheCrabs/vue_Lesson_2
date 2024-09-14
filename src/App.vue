<template>
  <main class="container">
    <Task1_2 />
    <Task3 />
    <Task4 />
    <div class="task-border" style="width: 450px;">
      <Task5 :result="message"/>
      <button type="button" class="btn btn-primary btn-massive" @click="changeMessage">Change message</button>
    </div>
    <Task6 />
    <Task7 />
    <Task8_10 />
    <Task11 />
  </main>
</template>

<script>
import Task1_2 from './components/Task1_2.vue';
import Task3 from './components/Task3.vue';
import Task4 from './components/Task4.vue';
import Task5 from './components/Task5.vue';
import Task6 from './components/Task6.vue';
import Task7 from './components/Task7.vue';
import Task8_10 from './components/Task8_10.vue';
import Task11 from './components/Task11.vue';


export default {
  components: {
    Task1_2,
    Task3,
    Task4,
    Task5,
    Task6,
    Task7,
    Task8_10,
    Task11
  },
  data() {
    return {
      message: 'This message for new component',
    }
  },
  methods: {
    changeMessage() {
      this.message = 'This message was change by methods'
    }
  }
}
</script>

<style lang="css" scoped>
</style>
