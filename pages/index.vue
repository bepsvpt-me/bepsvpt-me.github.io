<template>
  <main>
    <section>
      <embedded-image
        alt="logo"
        class="inline-block w-full md:w-64"
        :origin="require('~/assets/img/logo.jpg')"
        :src="require('~/assets/img/logo.webp')"
      />

      <div class="sm:ml-4 sm:inline-block align-top">
        <h1>bepsvpt</h1>

        <h2 class="mt-3">Email</h2>

        <hidden-info :value="email" />
      </div>
    </section>

    <section>
      <article v-for="group in groups" :key="group.key" class="mt-3">
        <h2 v-text="group.name" />

        <hr />

        <links-list :items="$data[group.key]" />
      </article>
    </section>
  </main>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  data: () => ({
    email: 'hello@infinitefa.email',

    groups: [
      { name: 'Links', key: 'links' },
      { name: 'Project Sites', key: 'projects' },
      { name: 'Packages', key: 'packages' },
      { name: 'Experiments', key: 'experiments' },
      { name: 'Archived', key: 'archived' },
    ],

    links: [
      {
        to: 'https://blog.bepsvpt.me',
        text: 'Blog',
      },
      {
        to: 'https://github.com/bepsvpt',
        text: 'GitHub',
      },
    ],

    projects: [
      {
        to: 'https://ccu.plus',
        text: 'CCU PLUS',
        description: 'Course review for National Chung Cheng University.',
      },
      {
        to: 'https://laravel.bepsvpt.me',
        text: 'Top Laravel Packages',
        description: ' List top 1,000 downloads Laravel packages.',
      },
    ],

    packages: [
      {
        to: 'https://github.com/bepsvpt/secure-headers',
        text: 'PHP Secure Headers',
        description: 'Add security related headers to HTTP response.',
      },
      {
        to: 'https://github.com/bepsvpt/blurhash',
        text: 'PHP BlurHash',
        description: 'A PHP implementation of BlurHash.',
      },
    ],

    experiments: [
      {
        to: 'https://github.com/bepsvpt/homebrew-updater',
        text: 'Homebrew Updater',
        description: 'Automatically check release of Homebrew formulas.',
      },
      {
        to: 'https://github.com/bepsvpt-me/remote-browser',
        text: 'Remote Browser',
        description: 'Use WebRTC to stream remote server puppeteer.',
      },
    ],

    archived: [
      {
        to: 'https://github.com/bepsvpt-me/bookwalker',
        text: 'BookWalker Searcher',
        description: 'Taiwan BOOK☆WALKER search tool.',
      },
      {
        to: 'https://github.com/bepsvpt-me/minecraft',
        text: 'Minecraft Server',
        description: 'My minecraft server info.',
      },
      {
        to: 'https://github.com/bepsvpt-me/youtuber',
        text: 'YouTuber Statistics',
        description: 'Track YouTuber channel and video statistics.',
      },
    ],
  }),
})
</script>
