<script setup lang="ts">
import { PlusCircleIcon, XMarkIcon } from '@heroicons/vue/24/solid'

const emit = defineEmits(['remove'])

defineProps<{
  name: string
  imageSrc?: string
  isPlaceholder?: boolean
  customClass?: string
  removable?: boolean
}>()
</script>

<template>
  <div
    v-if="isPlaceholder"
    class="flex-1 flex flex-col items-center justify-center px-4 py-3 rounded-lg bg-white/30 text-gray-800 font-bold shadow transition hover:bg-white/40 cursor-pointer max-h-32 border border-white/70"
    :class="customClass"
  >
    <PlusCircleIcon class="w-6 h-6 mb-1" />
    <span class="text-xs text-center">{{ name }}</span>
  </div>

  <div
    v-else
    class="flex-1 relative overflow-hidden flex flex-col items-start px-4 py-3 rounded-lg bg-white/30 text-gray-800 font-medium shadow transition hover:bg-white/40 cursor-pointer max-h-32 border border-white/70"
    :class="customClass"
  >
    <div class="flex items-center w-full">
      <span class="text-base">{{ name }}</span>
      <img
        v-if="imageSrc"
        :src="imageSrc"
        :alt="name"
        class="size-10 object-contain ml-auto"
      />
    </div>

    <button
      v-if="removable"
      @click.stop="emit('remove')"
      class="absolute top-1 right-1 p-1 rounded-full  transition"
      title="Retirer des favoris"
    >
      <XMarkIcon class="w-5 h-5 text-black hover:text-black/60" />
    </button>

    <div class="mt-1 w-full">
      <slot />
    </div>
  </div>
</template>


