<script setup lang="ts">
const personalSponsors = [
  {
    name: 'Marc Backes',
    avatar: 'https://avatars.githubusercontent.com/u/1444915?v=4',
    github: 'https://github.com/themarcba',
  },
  {
    name: 'bperel',
    avatar: 'https://avatars.githubusercontent.com/u/1484692?s=52&v=4',
    github: 'https://github.com/bperel',
  },
  {
    name: 'Silisav',
    avatar: 'https://avatars.githubusercontent.com/u/8262168?s=52&v=4',
    github: 'https://github.com/Silisav',
  },
  {
    name: 'robokozo',
    avatar: 'https://avatars.githubusercontent.com/u/1719221?s=52&v=4',
    github: 'https://github.com/robokozo',
  },
]

const tresSponsors = [
  {
    name: 'BboyAkers',
    avatar: 'https://avatars.githubusercontent.com/u/11778717?v=4',
    github: 'https://github.com/BboyAkers',
  },
  {
    name: 'FrankBevr',
    avatar: 'https://avatars.githubusercontent.com/u/30662393?s=52&v=4',
    github: 'https://github.com/FrankBevr',
  },
  {
    name: 'rodrigodjodi',
    avatar: 'https://avatars.githubusercontent.com/u/14154867?v=4',
    github: 'https://github.com/rodrigodjodi',
  },
  {
    name: 'Private E-Sports related',
    avatar: 'https://avatars.githubusercontent.com/u/126061441?s=52&v=4',
  },
]
</script>

<template>
  <section class="my-8 prose">
    <h3>
      TresJS
    </h3>
    <div class="flex flex-wrap gap-4">
      <div
        v-for="{ avatar } of tresSponsors"
        :key="avatar"
        class="flex flex-col items-center"
      >
        <img
          :src="avatar"
          class="important-rounded-full w-14 h-14 mb-2 object-cover shadow-xl"
        >
      </div>
    </div>
  </section>
  <section class="my-8 prose">
    <h3>
      Personal
    </h3>
    <div class="flex flex-wrap gap-4">
      <div
        v-for="{ avatar } of personalSponsors"
        :key="avatar"
        class="flex flex-col items-center"
      >
        <img
          :src="avatar"
          class="important-rounded-full w-14 h-14 mb-2 object-cover shadow-xl"
        >
      </div>
    </div>
  </section>
</template>
