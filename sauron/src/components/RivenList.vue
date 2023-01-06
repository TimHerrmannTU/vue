<script setup>
import RivenCard from './RivenCard.vue'

const rivens = [
    {
        weapon: "Astilla",
        name: "Sati-visicron",
        mr: 16,
        rank: 8,
        rolls: 0,
        price: 10000,
        endo: 3500,
        seller: "7vino",
        age: "13:51 19.12.22",
        graded: "Prime",
        url: "https://warframe.market/auction/639c7f554176ae059443448a",
        stats: [
            {pos: true, name: "dmg", value: "150%", grade: "A+"},
            {pos: true, name: "ms", value: "50%", grade: "F"},
            {pos: true, name: "cc", value: "150%", grade: "S"},
            {pos: false, name: "imp", value: "90%", grade: "C+"},
        ]
    },
    {
        weapon: "Kuva Twin Stubbas",
        name: "Sati-visicron",
        mr: 10,
        rank: 6,
        rolls: 15,
        price: 10000,
        endo: 3500,
        seller: "7vino",
        age: "13:51 19.12.22",
        graded: "Base",
        url: "https://warframe.market/auction/639c7f554176ae059443448a",
        stats: [
            {pos: true, name: "dmg", value: "150%", grade: "A+"},
            {pos: true, name: "ms", value: "50%", grade: "F"},
        ]
    }
]
</script>
<template>
    <div class="riven-list">
        <RivenCard v-for="riven in rivens" :riven=riven></RivenCard>
    </div>
</template>
<style>
.riven-list {
    display: flex;
    flex-direction: row;
    align-items: flex-start;
    justify-content: center;
}
.riven-list > .riven-card {
    margin: 1rem;
}
</style>