<template>
  <UHeader :toggle="false">
    <template #left>
      <UAvatar class="mr-2" size="sm" loading="lazy" src="img/profile.png" />
      <NuxtLink to="/">
        <p class="text-lg">Abel Iglesias Moure</p>
      </NuxtLink>
    </template>
    <template #right>
      <UButton to="https://www.linkedin.com/in/abel-iglesias-moure/" target="_blank" icon="streamline:linkedin" size="md" color="neutral" variant="ghost"></UButton>
      <UButton to="/pdf/abel_iglesias_moure.pdf" target="_blank" icon="tabler:file-cv" size="md" color="neutral" variant="ghost"></UButton>
      <UButton to="https://github.com/Abel-ADE" target="_blank" icon="i-lucide-github" size="md" color="neutral" variant="ghost"></UButton>
      <UColorModeButton />
    </template>
  </UHeader>
</template>
