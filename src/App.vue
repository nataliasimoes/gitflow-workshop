<script setup>
import Header from './components/Header.vue'
import Retronatus from './components/Retronatus.vue'
import Braincase from './components/Braincase.vue';

import { ref } from "vue";

const retronatusGrade = ref(null)
const braincaseGrade = ref(null)

function finishRetronatus(tasks){
  let grade = 10
  for(let task of tasks) {
    if(task.complete) {
      grade += 10
    }
  }
  retronatusGrade.value = grade
}

function finishBraincase(tasks){
  let grade = 25
  for(let task of tasks) {
    if(task.complete) {
      grade += 25
    }
  }
  braincaseGrade.value = grade
}

</script>

<template>
  <header>
    <img alt="Vue logo" class="logo" src="./assets/logo.svg" width="125" height="125" />

    <div class="wrapper">
      <Header />
    </div>
  </header>

  <main>
    <div class="col">
      <div>
        <h1 class="green">NOTA: 
          <span v-if="retronatusGrade !== null">{{ retronatusGrade }}</span>
          <span v-else>aguardando...</span>
        </h1>
        <Retronatus @finish="finishRetronatus" />
      </div>
    </div>
    <div class="col">
      <div>
        <h1 class="green">NOTA:
          <span v-if="braincaseGrade !== null">{{ braincaseGrade }}</span>
          <span v-else>aguardando...</span>
        </h1>
        <Braincase @finish="finishBraincase" />
      </div>
    </div>
  </main>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
