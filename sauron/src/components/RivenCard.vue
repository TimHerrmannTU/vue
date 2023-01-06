<script setup>
// vue meta
import platSVG from "./icons/IconPlat.vue"
defineProps({
  riven: {type: Object}
})
</script>
<template>
  <div class="riven-card" @click="open_details">
    <div class="header">
      <h3 class="name">
        {{riven.weapon}}<br>{{riven.name}}
      </h3>
      <i><slot name="polarity"></slot></i>
    </div>
    <div class="table-wrapper">
      <table class="stats">
        <tr v-for="stat in riven.stats" v-bind:class="(stat.pos) ? 'pos' : 'neg'">
          <td class="spacer"></td>
          <td>{{stat.value}}</td>
          <td>{{stat.name}}</td>
          <td v-bind:class="(stat.grade).replace('+', '').replace('-', '')">{{stat.grade}}</td>
          <td class="spacer"></td>
        </tr>
        <tr></tr>
      </table>
      <p class="tiny-text" style="margin-top: -0.3rem"><strong>{{riven.graded}}</strong> grades</p>
    </div>
    <div class="misc-stats small-text">
      <div><strong>MR</strong>{{riven.mr}}</div>
      <div><strong>R</strong>{{riven.rank}}</div>
      <div v-bind:class="(riven.rolls) == 0 ? 'unrolled' : ''">{{riven.rolls}}<!--<i class="fas fa-undo-alt"></i>--></div>
    </div>
    <div class="important">
      <div class="price"><strong>{{riven.price}}</strong><platSVG/></div>
      <div class="small-text spaced">
        <span><strong>IGN: </strong>{{riven.seller}}</span>
        <span>{{riven.endo}} endo/pl</span>
      </div>
      <div class="tiny-text">{{riven.age}}</div>
    </div>
  </div>
</template>

<style>
:root {
  --pseudo-border: 0.4rem;
  --primary: rgb(50, 50, 50);
  --secondary: rgb(70, 70, 70);
  --tertiary: rgb(150, 150, 150);
  --quaternary: rgb(200, 200, 200);
  --pos-green: #c8ffc8;
  --neg-red: #ffc8c8;
}
.riven-card {
  width: 12rem;
  border-radius: 0.2rem;
  overflow: hidden;
  display: flex;
  flex-direction: column;
  align-items: center;
  font-size: 1rem;
  box-shadow: rgba(50, 50, 93, 0.25) 0px 2px 5px -1px, rgba(0, 0, 0, 0.3) 0px 1px 3px -1px;
  color: var(--tertiary);
  background-color: var(--secondary);
}
.riven-card .header, .riven-card .misc-stats {
  background-color: var(--primary);
}
.riven-card .important {
  padding: 0rem var(--pseudo-border);
  background-color: var(--vt-c-white);
  color: var(--primary);
}
.riven-card .important strong {
  color: black;
}
.riven-card .header {
  color: var(--quaternary);
  font-size: 1.2rem;
  font-weight: 900;
  line-height: 1.3rem;
  letter-spacing: 2px;
  padding-bottom: 0.5rem;
}
.riven-card > * {
  width: 100%;
  padding: 0 var(--pseudo-border);
}
.riven-card > :first-child {
  padding-top: var(--pseudo-border);
}
.riven-card > :last-child {
  padding-bottom: var(--pseudo-border)
}
.riven-card * {
  text-align: center;
}
.riven-card .table-wrapper {
  display: flex;
  flex-direction: column;
  justify-content: center;
  width: 100%;
  border: 0 solid var(--primary);
  border-width: 0 var(--pseudo-border);
}
.riven-card .table-wrapper td {
  width: 1%;
  white-space: nowrap;
  line-height: 1.4rem;
  padding: 0rem 0.2rem;
}
.riven-card .table-wrapper td.spacer {
  width: auto;
}
.riven-card .stats tr > * {
  text-align: left;
}
.riven-card .stats tr > td:first-of-type {
  text-align: right;
}
.pos {
  color: var(--pos-green)
}
.neg {
  color: var(--neg-red)
}
.riven-card .misc-stats {
  display: flex;
  flex-direction: row;
  justify-content: space-evenly;
  padding: 0 15%;
}
.riven-card .important .price {
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
}
.riven-card .important .plat-icon {
  stroke: var(--secondary);
  fill: var(--secondary);
  width: 1rem;
  margin-left: 0.3rem;
}
.small-text {
  font-size: 0.8rem;
}
.tiny-text {
  font-size: 0.6rem;
}
.spaced {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
}
.unrolled {
  color: var(--quaternary);
}
strong {
  color: var(--quaternary)
}
</style>