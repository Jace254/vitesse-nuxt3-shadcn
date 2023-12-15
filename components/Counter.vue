<script setup lang='ts'>
import { Button } from '@/components/ui/button'

const { count, inc, dec } = useCount()
</script>

<template>
  <div inline-flex m="y-3">
    <Button variant="outline" @click="dec()">
      <div i-carbon-subtract />
    </Button>
    <div font="mono" w="15" m-auto inline-block>
      {{ count }}
    </div>
    <Button variant="outline" @click="inc()">
      <div i-carbon-add />
    </Button>
  </div>
</template>
