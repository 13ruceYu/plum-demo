<script lang="ts" setup>
const el = $ref<HTMLCanvasElement>()
const ctx = $computed(() => el!.getContext('2d')!)

function init() {
  ctx.strokeStyle = '#fff'
  line(0, 0, 30, 30)
}

function line(x1: number, y1: number, x2: number, y2: number) {
  ctx.beginPath()
  ctx.moveTo(x1, y1)
  ctx.lineTo(x2, y2)
  ctx.stroke()
}

onMounted(() => {
  init()
})
</script>

<template>
  <canvas ref="el" width="400" height="400" border />
</template>
