<template>
  <template v-for="arrowSet in arrows">
    <FancyArrow
        v-for="(arrow, index) in arrowSet"
        :key="index"
        v-click="arrow.click"
        :from="from(arrow.to, arrow.tailOffset)"
        :to="to(arrow.to)"
        :arc="arrow.arc"
        :color="arrow.color"
        roughness="1"
        bowing="0.1"
        width="3"
        :animation-delay="250 * index"
        :seed="arrow.seed"
    />
  </template>
</template>

<script lang="ts" setup>
import FancyArrow from 'slidev-addon-fancy-arrow/components/FancyArrow.vue'

const arrows = [
  [
    {
      seed: 1,
      click: [4, 6],
      tailOffset: [-50, 70],
      to: [190, 140],
      arc: "-0.1",
      color: 'yellow'
    },
    {
      seed: 2,
      click: [4, 6],
      tailOffset: [20, 60],
      to: [780, 140],
      arc: "0.2",
      color: 'yellow'
    },
    {
      click: [4, 6],
      tailOffset: [70, 10],
      to: [720, 50],
      arc: "-0.1",
      color: 'yellow'
    },
    {
      seed: 5,
      click: [4, 6],
      tailOffset: [140, 0],
      to: [540, 260],
      arc: "0.1",
      color: 'yellow'
    },
    {
      seed: 6,
      click: [4, 6],
      tailOffset: [-75, 35],
      to: [375, 165],
      arc: "0.1",
      color: 'yellow'
    },
    {
      seed: 4,
      click: [4, 6],
      tailOffset: [-100, -35],
      to: [400, 315],
      arc: "-0.2",
      color: 'yellow'
    },
    {
      seed: 3,
      click: [4, 6],
      tailOffset: [-55, 60],
      to: [135, 110],
      arc: "0.3",
      color: 'yellow'
    },
  ],
  [
    {
      seed: 1,
      click: [5, 6],
      tailOffset: [-50, 70],
      to: [190, 140],
      arc: "-0.1",
      color: '[#50b5f7]' // text-[#50b5f7]
    },
    {
      click: [5, 6],
      tailOffset: [-50, 50],
      to: [290, 130],
      arc: "-0.1",
      color: '[#50b5f7]'
    },
    {
      seed: 2,
      click: [5, 6],
      tailOffset: [20, 60],
      to: [780, 140],
      arc: "0.2",
      color: '[#ff773a]' // text-[#ff773a]
    },
    {
      click: [5, 6],
      tailOffset: [30, 50],
      to: [680, 130],
      arc: "-0.1",
      color: '[#ff773a]'
    },
    {
      seed: 3,
      click: [5, 6],
      tailOffset: [-55, 60],
      to: [135, 110],
      arc: "0.3",
      color: 'green'
    },
    {
      click: [5, 6],
      tailOffset: [-10, -70],
      to: [490, 130],
      arc: "0.1",
      color: 'green'
    },
    {
      click: [5, 6],
      tailOffset: [-60, 35],
      to: [440, 220],
      arc: "-0.2",
      color: 'green'
    },
    {
      seed: 4,
      click: [5, 6],
      tailOffset: [-100, -35],
      to: [400, 315],
      arc: "-0.2",
      color: 'purple'
    },
    {
      click: [5, 6],
      tailOffset: [80, 45],
      to: [490, 360],
      arc: "0.2",
      color: 'purple'
    },
    {
      seed: 5,
      click: [5, 6],
      tailOffset: [140, 0],
      to: [540, 260],
      arc: "0.1",
      color: 'cyan'
    },
    {
      seed: 6,
      click: [5, 6],
      tailOffset: [-75, 35],
      to: [375, 165],
      arc: "0.1",
      color: 'gray'
    },
  ]
]

function from(to: number[], offset: number[]) {
  const from = [to[0] + offset[0], to[1] + offset[1]]

  return `(${ from[0] },${ from[1] })`
}

function to(to: number[]) {
  return `(${ to[0] },${ to[1] })`
}
</script>
