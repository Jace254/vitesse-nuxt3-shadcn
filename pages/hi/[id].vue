<script setup lang="ts">
import { Button } from '@/components/ui/button'

const route = useRoute<'hi-id'>()
const user = useUserStore()
const name = route.params.id

watchEffect(() => {
  user.setNewName(route.params.id as string)
})

definePageMeta({
  layout: 'home',
})
</script>

<template>
  <div>
    <div i-twemoji:waving-hand inline-block animate-shake-x animate-duration-5000 text-4xl />
    <h3 text-2xl font-500>
      Hi,
    </h3>
    <div text-xl>
      {{ name }}!
    </div>

    <template v-if="user.otherNames.length">
      <p my-4 text-sm>
        <span op-50>Also as known as:</span>
        <ul>
          <li v-for="otherName in user.otherNames" :key="otherName">
            <router-link :to="`/hi/${otherName}`" replace>
              {{ otherName }}
            </router-link>
          </li>
        </ul>
      </p>
    </template>

    <Counter />

    <div>
      <Button :as-child="true">
        <NuxtLink
          to="/"
        >
          Back
        </NuxtLink>
      </Button>
    </div>
  </div>
</template>
