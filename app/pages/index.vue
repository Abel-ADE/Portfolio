<template>
  <UPage>
    <UPageCTA>
      <template #header>
        <UContainer class="flex flex-col items-center text-center gap-6">
          <UColorModeImage light="img/profile.png" dark="img/profile.png"
            class="rounded-full mx-auto w-16 md:w-20 lg:w-24" />
          <h1 class="text-4xl font-bold text-neutral-800 dark:text-neutral-100">Abel Iglesias Moure</h1>
          <h2>Tecnología y Empresas</h2>
          <p>Me muevo entre dos mundos: la empresa y la tecnología. Me gusta ganar habilidades en el área tecnológica, a
            la par que voy ganando experiencia en administración y gestión empresarial.</p>
        </UContainer>
      </template>
      <template #footer>
        <UContainer class="flex justify-center gap-6">
          <UButton class="cursor-pointer" to="#projects" color="primary" variant="outline" size="lg">Proyectos</UButton>
          <UButton class="cursor-pointer" to="#contact" color="neutral" variant="outline" size="lg">Contacto</UButton>
        </UContainer>
      </template>
    </UPageCTA>

    <UPageSection id="technologies" title="Tecnologías" :ui="{ title: 'text-3xl sm:text-3xl lg:text-4xl' }">
      <template #default>
        <UMarquee>
          <MyPopoverIcon size="size-8" nameIcon="vscode-icons:file-type-vscode" textContent="Visual Studio Code" />
          <MyPopoverIcon size="size-8" nameIcon="vscode-icons:file-type-html" textContent="HTML 5" />
          <MyPopoverIcon size="size-8" nameIcon="vscode-icons:file-type-css2" textContent="CSS 3" />
          <MyPopoverIcon size="size-8" nameIcon="vscode-icons:file-type-js-official" textContent="JavaScript" />
          <MyPopoverIcon size="size-8" nameIcon="vscode-icons:file-type-vue" textContent="Vue" />
          <MyPopoverIcon size="size-8" nameIcon="vscode-icons:file-type-nuxt" textContent="Nuxt" />
          <MyPopoverIcon size="size-8" nameIcon="logos:supabase-icon" textContent="Supabase" />
        </UMarquee>
      </template>
    </UPageSection>

    <UPageSection id="projects" title="Proyectos" :ui="{ title: 'text-3xl sm:text-3xl lg:text-4xl' }">
      <UPageColumns>
        <template>
          <UEmpty title="Escalas de enfermería"
            description="Web con escalas de enfermería en formato formulario, ofrece la puntuación final de la escala y una pequeña valoración"
            :actions="[
              {
                label: 'Ver proyecto',
                to: 'https://escalasenfermeria.com/',
                target: '_blank'
              },
              {
                icon: 'i-lucide:github',
                label: 'Ver repositorio',
                color: 'neutral',
                variant: 'outline',
                to: 'https://github.com/Abel-ADE/NuxtUi4/',
                target: '_blank'
              }
            ]">
            <template #description>
              <p>Web con escalas de enfermería en formato formulario, ofrece la puntuación final de la escala y una
                pequeña valoración</p>
              <div class="flex justify-center gap-2 pt-4 pb-2">
                <MyPopoverIcon size="size-4" nameIcon="vscode-icons:file-type-vscode"
                  textContent="Visual Studio Code" />
                <MyPopoverIcon size="size-4" nameIcon="vscode-icons:file-type-html" textContent="HTML 5" />
                <MyPopoverIcon size="size-4" nameIcon="vscode-icons:file-type-css2" textContent="CSS 3" />
                <MyPopoverIcon size="size-4" nameIcon="vscode-icons:file-type-js-official" textContent="JavaScript" />
                <MyPopoverIcon size="size-4" nameIcon="vscode-icons:file-type-vue" textContent="Vue" />
                <MyPopoverIcon size="size-4" nameIcon="vscode-icons:file-type-nuxt" textContent="Nuxt" />
                <MyPopoverIcon size="size-4" nameIcon="logos:supabase-icon" textContent="Supabase" />
              </div>
            </template>
          </UEmpty>
        </template>

      </UPageColumns>
    </UPageSection>

    <UPageSection id="about" title="Sobre mí" :ui="{ title: 'text-3xl sm:text-3xl lg:text-4xl' }"
      description="Nuxt UI provides a comprehensive suite of components and utilities to help you build beautiful and accessible web applications with Vue and Nuxt."
      icon="i-lucide-rocket">
      <template #description>
        <div class="flex flex-col gap-6">
          <p>
            Mi formación en Administración y Dirección de Empresas me permitió conocer de cerca la gestión, las finanzas
            y el funcionamiento de las organizaciones. Al mismo tiempo, mi interés por la informática y las nuevas
            tecnologías fue creciendo, despertando en mí la curiosidad por comprender cómo funcionan y cómo pueden
            aplicarse para resolver problemas y mejorar procesos.
          </p>
        </div>
      </template>
    </UPageSection>

    <UPageSection id="experience" title="Experiencia destacada" :ui="{ title: 'text-3xl sm:text-3xl lg:text-4xl' }">
      <UTimeline size="3xl" :ui="{ root: 'mx-auto' }" :items="[
        {
          date: '12/12/2025 - Actualmente',
          title: 'Administrativo comercial',
          description: 'Administrativo en el área comercial de la empresa, con gestión de cartera de clientes B2B.',
          avatar: {
            src: 'img/rosales.png',
          }
        },
        {
          date: '01/12/24 - 12/12/25',
          title: 'Team Leader Automoción',
          description: 'Jefe de equipo en departamento de producción, con 7 operarios a cargo.',
          avatar: {
            src: 'img/stellantis.png',
          }
        },
      ]" />
      <UButton :ui="{base: 'w-fit mx-auto'}" to="/pdf/abel_iglesias_moure.pdf" target="_blank" icon="tabler:file-cv" size="md" color="neutral" variant="outline">Ver Currículum</UButton>
    </UPageSection>

    <UPageSection id="contact" title="Contacto" description="¿Hablamos?"
      :ui="{ title: 'text-3xl sm:text-3xl lg:text-4xl' }">
      <div class="w-full md:w-1/2 mx-auto flex flex-col gap-4">
        <UInput readonly v-model="value"
          :ui="{ trailing: 'pr-0.5', root: 'w-full', base: 'text-center' }">
          <template v-if="value?.length" #trailing>
              <UButton :color="copied ? 'success' : 'neutral'" variant="link" size="sm"
                :icon="copied ? 'i-lucide-copy-check' : 'i-lucide-copy'" aria-label="Copy to clipboard"
                @click="copy(value); toast.add({title: '¡Correo electrónico copiado!', description: 'Ahora puedes ir a tu gestor de correo y enviarme un e-mail. Gracias por visitar mi portfolio.', icon:'i-lucide-mail', duration:5000})" />
          </template>
        </UInput>
        <div class="w-full flex gap-4 justify-between">
          <UButton :ui="{base: 'w-full items-center justify-center align-middle'}"  to="https://www.linkedin.com/in/abel-iglesias-moure/" target="_blank" icon="streamline:linkedin"
            size="md" label="Linkedin" color="neutral" variant="outline"></UButton>
            <UButton :ui="{base: 'w-full items-center justify-center align-middle'}"  to="https://www.linkedin.com/in/abel-iglesias-moure/" target="_blank" icon="i-lucide-github"
            size="md" label="Github" color="neutral" variant="outline"></UButton>
        </div>
      </div>
    </UPageSection>
  </UPage>
</template>

<script setup lang="ts">
import { useClipboard } from '@vueuse/core'

const toast = useToast()

const value = ref('abeliglesiasmoure@gmail.com')

const { copy, copied } = useClipboard();
</script>
