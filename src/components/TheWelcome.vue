<template>
  <template v-for="introItem in vueMenuIntro">
    <template v-if="!introItem.disabled">
      <WelcomeItem>
        <template #heading>{{ introItem.heading }}</template>
        {{ introItem.description }}
      </WelcomeItem>
    </template>
  </template>
</template>
<script setup lang="ts">
import WelcomeItem from './WelcomeItem.vue';
interface IMenuIntro {
  heading: string;
  description: string;
  disabled: boolean;
}
// 也可以寫成 const vueMenuIntro: Array<IMenuIntro>
const vueMenuIntro: IMenuIntro[] = [
  {
    heading: 'Documentation',
    description: 'Vue’s official documentation provides you with all information you need to get started.',
    disabled: false,
  },
  {
    heading: 'Tooling',
    description:
      'This project is served and bundled with Vite. The recommended IDE setup is VSCode + Volar. If you need to test your components and web pages, check out Cypress and Cypress Component Testing. More instructions are available in README.md.',
    disabled: true,
  },
  {
    heading: 'Ecosystem',
    description:
      'Get official tools and libraries for your project: Pinia, Vue Router, Vue Test Utils, and Vue Dev Tools. If you need more resources, we suggest paying Awesome Vue a visit.',
    disabled: false,
  },
  {
    heading: 'Community',
    description:
      'Got stuck? Ask your question on Vue Land, our official Discord server, or StackOverflow. You should also subscribe to our mailing list and follow the official @vuejs twitter account for latest news in the Vue world.',
    disabled: false,
  },
  {
    heading: 'Support Vue',
    description:
      'As an independent project, Vue relies on community backing for its sustainability. You can help us by becoming a sponsor.',
    disabled: false,
  },
];
</script>
