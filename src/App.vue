<template>
  <div>
    <Beverage :isIced="currentTemp === 'Cold'" />
    <ul>
      <li>
        <template v-for="temp in temps" :key="temp">
          <label>
            <input
              type="radio"
              name="temperature"
              :id="`r${temp}`"
              :value="temp"
              v-model="currentTemp"
            />
            {{ temp }}
          </label>
        </template>
      </li>
    </ul>
<h3>Base Beverage</h3>
<label v-for="base in bases" :key="base.id">
  <input
    type="radio"
    name="base"
    :value="base"
    v-model="currentBase"
  />
  {{ base.name }}
</label>

<h3>Creamer</h3>
<label v-for="creamer in creamers" :key="creamer.id">
  <input
    type="radio"
    name="creamer"
    :value="creamer"
    v-model="currentCreamer"
  />
  {{ creamer.name }}
</label>

<h3>Syrup</h3>
<label v-for="syrup in syrups" :key="syrup.id">
  <input
    type="radio"
    name="syrup"
    :value="syrup"
    v-model="currentSyrup"
  />
  {{ syrup.name }}
</label>

  </div>
</template>

<script setup lang="ts">
import Beverage from "./components/Beverage.vue";
import {temps,bases,creamers,syrups,currentTemp,currentBase,currentCreamer,currentSyrup} from "./stores/beverage";
</script>

<style lang="scss">
body,
html {
  position: relative;
  display: flex;
  align-items: center;
  justify-content: center;
  height: 100%;
  background-color: #6e4228;
  background: linear-gradient(to bottom, #6e4228 0%, #956f5a 100%);
}
ul {
  list-style: none;
}
</style>
