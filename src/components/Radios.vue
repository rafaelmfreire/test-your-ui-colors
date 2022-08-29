<template>
  <div class="w-full px-4 py-16 bg-card rounded-md">
    <div class="mx-auto w-full max-w-md">
      <RadioGroup v-model="selected">
        <RadioGroupLabel class="sr-only">Server size</RadioGroupLabel>
        <div class="space-y-2">
          <RadioGroupOption
            as="template"
            v-for="plan in plans"
            :key="plan.name"
            :value="plan"
            v-slot="{ active, checked }"
          >
            <div
              :class="[
                active
                  ? 'ring-2 ring-white ring-opacity-60 ring-offset-2 active'
                  : '',
                checked ? 'selected bg-opacity-75' : 'bg-white ',
              ]"
              class="relative flex cursor-pointer rounded-lg px-5 py-4 shadow-md focus:outline-none"
            >
              <div class="flex w-full items-center justify-between">
                <div class="flex items-center">
                  <div class="text-sm">
                    <RadioGroupLabel
                      as="p"
                      :class="checked ? 'selected' : 'text-gray-900'"
                      class="font-medium"
                    >
                      {{ plan.name }}
                    </RadioGroupLabel>
                    <RadioGroupDescription
                      as="span"
                      :class="checked ? 'selected' : 'text-gray-500'"
                      class="inline"
                    >
                      <span> {{ plan.ram }}/{{ plan.cpus }}</span>
                      <span aria-hidden="true"> &middot; </span>
                      <span>{{ plan.disk }}</span>
                    </RadioGroupDescription>
                  </div>
                </div>
                <div v-show="checked" class="shrink-0 text-white">
                  <svg class="h-6 w-6" viewBox="0 0 24 24" fill="none">
                    <circle
                      cx="12"
                      cy="12"
                      r="12"
                      fill="#fff"
                      fill-opacity="0.2"
                    />
                    <path
                      d="M7 13l3 3 7-7"
                      stroke="#fff"
                      stroke-width="1.5"
                      stroke-linecap="round"
                      stroke-linejoin="round"
                    />
                  </svg>
                </div>
              </div>
            </div>
          </RadioGroupOption>
        </div>
      </RadioGroup>
    </div>
  </div>
</template>

<script setup>
import { ref, computed } from 'vue'
import {
  RadioGroup,
  RadioGroupLabel,
  RadioGroupDescription,
  RadioGroupOption,
} from '@headlessui/vue'

const props = defineProps(['primary', 'secondary', 'label'])

const hexToRgba = computed(() => {
   let hex   = props.primary.replace('#', '');
   let alpha = '0.05';
   var r = parseInt(hex.length == 3 ? hex.slice(0, 1).repeat(2) : hex.slice(0, 2), 16);
   var g = parseInt(hex.length == 3 ? hex.slice(1, 2).repeat(2) : hex.slice(2, 4), 16);
   var b = parseInt(hex.length == 3 ? hex.slice(2, 3).repeat(2) : hex.slice(4, 6), 16);
  //  if ( alpha ) {
      return 'rgba(' + r + ', ' + g + ', ' + b + ', ' + alpha + ')';
  //  }
  //  else {
      // return 'rgb(' + r + ', ' + g + ', ' + b + ')';
  //  }
})

const plans = [
  {
    name: 'Startup',
    ram: '12GB',
    cpus: '6 CPUs',
    disk: '160 GB SSD disk',
  },
  {
    name: 'Business',
    ram: '16GB',
    cpus: '8 CPUs',
    disk: '512 GB SSD disk',
  },
  {
    name: 'Enterprise',
    ram: '32GB',
    cpus: '12 CPUs',
    disk: '1024 GB SSD disk',
  },
]

const selected = ref(plans[0])
</script>
<style scoped>
.selected {
	background-color: v-bind('props.primary');
	color: v-bind('props.secondary');
}
.active {
	box-shadow: 0 0 0 var(--tw-ring-offset-width) v-bind('props.primary'), var(--tw-ring-shadow);
}
.bg-card {
  background-color: v-bind('hexToRgba');
}
</style>