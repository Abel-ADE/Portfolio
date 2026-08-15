<template>
    <UPopover class="cursor-pointer">
        <UIcon label="Open" :name="nameIcon" :class="size" />
        <template #content>
            <p class="p-2">{{ textContent }}</p>
        </template>
    </UPopover>
</template>

<script setup lang="ts">
interface Props {
    nameIcon: string;
    textContent: string;
    size: `size-${number}`;
}

const {nameIcon, textContent, size} = defineProps<Props>();
</script>