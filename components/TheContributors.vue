<script setup lang="ts">
import { onMounted, ref } from 'vue'

const repos = [
  'https://api.github.com/repos/tresjs/tres/contributors',
  'https://api.github.com/repos/tresjs/cientos/contributors',
  'https://api.github.com/repos/tresjs/post-processing/contributors',
  'https://api.github.com/repos/tresjs/nuxt/contributors',
  'https://api.github.com/repos/tresjs/rapier/contributors',
  // Add more repository URLs here
]

const contributors = ref([])

onMounted(async () => {
  const data = await Promise.all(repos.map(url => fetch(url)))
  const json = await Promise.all(data.map(res => res.json()))
  const flattened = json.flat()
  const sorted = flattened.sort((a, b) => b.contributions - a.contributions)
  const usernames = sorted.map(contributor => contributor.login)
  contributors.value = [...new Set(usernames)]
})
</script>

<template>
  <div class="pt-8 flex gap-8 flex-wrap">
    <div
      v-for="username of contributors"
      :key="username"
      class="flex flex-col items-center  overflow-hidden"
    >
      <img
        :title="username"
        :src="`https://avatars.githubusercontent.com/${username}?v=4`"
        class="important-rounded-full w-14 h-14 mb-2 object-cover shadow-xl"
      />
    </div>
  </div>
</template>
