<template>
    <!-- :class="enabled ? 'on' : 'bg-red-500'" -->
  <Switch
    v-model="enabled"
    :style='enabled ? "background-color: "+props.primary : "background-color: #dddddd"'
    class="relative inline-flex h-6 w-11 items-center rounded-full ring-1 ring-black/20"
  >
    <span class="sr-only">Enable notifications</span>
    <span
      :class="enabled ? 'translate-x-6' : 'translate-x-1'"
      class="inline-block h-4 w-4 rounded-full bg-white transform transition duration-200 ease-in-out"
    />
  </Switch>
</template>

<script setup>
  import { ref, reactive } from 'vue'
  import { Switch } from '@headlessui/vue'

  const props = defineProps(['primary', 'secondary', 'label'])

  const enabled = ref(true)
</script>