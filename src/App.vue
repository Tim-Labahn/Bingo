<script setup lang="ts">
import Card from "./components/Card.vue";
let tileContent = [
  "FreeSpace",
  "Lehrer geht raus",
  "Zug kommt zu spät",
  "Es wird 5 mal laut penis gerufen",
  "Irgendwelche privaten Stroys von Lehrern",
  "Torben macht Dad Jokes",
  "Niklas kommt pünklich",
  "Gruppenarbeit",
  "Tafel wird genutzt",
  "Thema Jans Frisur",
  "Timo ist da",
  "Anu geht für eine längere Zeit raus",
  "Laptops zu!",
  "Tim L. vergist einen Namen",
  "Bahn Streik/ Verspätung",
  "Niklas shcrottet sein auto",
  "Shameless Joke",
  "Irgendwas fällt aus",
  "Hr. Bechmann rastet aus",
  "Einer Fährt Fastfood holen (Pizza, Dönner, Mcs...)",
  "Christiansen kommt Random rein",
  "Helge lässt und früher gehen",
  "Fabian hat Salat dabei",
  "Jonas sagt was!",
  "Wir machen keein Unterricht",
  "Nikita sagt was zum thema Frauen",
  "Chantal sagt Lapi",
  "Jemand hat die präsi vergessen",
  "Jemand hat Zugangsdaten vergessen",
];

let card = [];
for (let i = 0; i < 5; i++) {
  let row = [];
  for (let i = 0; i < 5; i++) {
    let randomIndex = Math.floor(Math.random() * tileContent.length);
    row.push(tileContent[randomIndex]);
    tileContent.splice(randomIndex, 1);
  }
  card.push(row);
}
console.log(card);

let bingoCard = card;
</script>

<template>
  <Card :card="bingoCard" />
</template>
