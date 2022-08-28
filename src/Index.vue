<script setup>
import { reactive } from 'vue'
import PrimaryButton from './components/PrimaryButton.vue'
import SecondaryButton from './components/SecondaryButton.vue'
import Checkboxes from './components/Checkboxes.vue'
import Toggle from './components/Toggle.vue'
import Radios from './components/Radios.vue'

const colors = reactive({ 
  primary: "#4f46e5",
  secondary: "#ffffff",
  label: 'Label'
})

</script>

<template>
<div class="max-w-5xl mx-auto py-12">
    
  <div class="grid grid-cols-4 gap-4">
    <div>
      <label for="primary" class="block text-sm font-medium text-gray-700">Primary</label>
      <div class="mt-1 relative rounded-md shadow-sm">
        <input type="text" v-model="colors.primary" name="primary" id="primary" class="focus:ring-indigo-500 focus:border-indigo-500 block w-full sm:text-sm border-gray-300 rounded-md">
        <div class="absolute inset-y-0 right-2 flex items-center">
          <input type="color" v-model="colors.primary">
        </div>
      </div>
    </div>
    <div>
      <label for="secondary" class="block text-sm font-medium text-gray-700">Secondary</label>
      <div class="mt-1 relative rounded-md shadow-sm">
        <input type="text" v-model="colors.secondary" name="secondary" id="secondary" class="focus:ring-indigo-500 focus:border-indigo-500 block w-full sm:text-sm border-gray-300 rounded-md">
        <div class="absolute inset-y-0 right-2 flex items-center">
          <input type="color" v-model="colors.secondary">
        </div>
      </div>
    </div>
    <div>
      <label for="label" class="block text-sm font-medium text-gray-700">Label</label>
      <div class="mt-1 relative rounded-md shadow-sm">
        <input type="text" v-model="colors.label" name="label" id="label" class="focus:ring-indigo-500 focus:border-indigo-500 block w-full sm:text-sm border-gray-300 rounded-md">
      </div>
    </div>
  </div>

  <div class="h-10"></div>
  <div class="space-x-4">
    <PrimaryButton :label="colors.label" :primary="colors.primary" :secondary="colors.secondary" />
    <SecondaryButton :label="colors.label" :primary="colors.primary" :secondary="colors.secondary" />
    <Toggle :enabled="true" :primary="colors.primary" :secondary="colors.secondary" />
  </div>
  <div class="grid grid-cols-2 gap-4">
    <Checkboxes :primary="colors.primary" :secondary="colors.secondary" />
    <Radios :primary="colors.primary" :secondary="colors.secondary" />
  </div>
</div>
</template>