<script setup lang="ts">
import { ref } from 'vue';


const startTime = new Date(new Date().setHours(0, 0, 0, 0));
const currentTime = new Date();
const endTime = new Date(new Date().setHours(0, 0, 0, 0) + 24 * 60 * 60 * 1000 - 1);

const totalSeconds = Math.floor((endTime.getTime() - startTime.getTime()) / 1000);
const restSeconds = Math.floor((endTime.getTime() - currentTime.getTime()) / 1000);

const restPercent = Math.floor(restSeconds / totalSeconds * 100);

const time = ref(currentTime);
function Timer() {

}

</script>

<template>
  <section>
    <div class="line-box">
      <div class="line-inner" :style="{height: `${restPercent}%`}"></div>
    </div>
  </section>
</template>

<style>
section {
  display: flex;
  align-items: center;
  justify-content: center;
}

.line-box {
  width: 10em;
  height: 24em;
  border: 1px solid tomato;
  display: flex;
  align-items: flex-end;
}

.line-inner {
  width: 100%;
  background: #296bef;
}
</style>
