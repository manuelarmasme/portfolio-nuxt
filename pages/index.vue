import { NuxtLink } from '../.nuxt/components';
<template>
  <nav>
    <ul>
      <li>
        <NuxtLink to="/">Main</NuxtLink>
      </li>
      <li>
        <NuxtLink to="/about">About</NuxtLink>
      </li>
    </ul>
  </nav>
  <div>
    I'm index page
  </div>
</template>