<script setup lang="ts">
import { Button } from '@/components/ui/button';

const router = useRouter()
</script>

<template>
  <main p="x4 y10" text="center teal-700 dark:gray-200">
    <div text-4xl>
      <div i-carbon-warning inline-block />
    </div>
    <div>Not found</div>
    <div>
      <Button m="3 t8" @click="router.back()">
        Back
      </Button>
    </div>
  </main>
</template>
