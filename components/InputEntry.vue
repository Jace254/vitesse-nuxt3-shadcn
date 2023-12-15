<script setup lang="ts">
import { Input } from '@/components/ui/input'
import { Button } from '@/components/ui/button'

const name = ref('')

const router = useRouter()
function go() {
  if (name.value)
    router.push(`/hi/${encodeURIComponent(name.value)}`)
}
</script>

<template>
  <div>
    <Input
      id="input"
      v-model="name"
      m-auto
      max-w="460px"
      placeholder="What's your name?"
      @keydown.enter="go"
    />

    <div>
      <Button
        :disabled="!name"
        @click="go"
      >
        GO
      </Button>
    </div>
  </div>
</template>
