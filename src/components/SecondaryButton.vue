<template>
	<button class="bg-white py-2 px-4 border-2 rounded-md shadow-sm text-sm font-medium focus:outline-none focus:ring-2 focus:ring-offset-2 transition-all duration-300 ease-in-out">{{ label }}</button>
</template>

<script setup>
import { reactive } from "@vue/reactivity"

const props = defineProps(['primary', 'secondary', 'label'])

</script>
<style scoped>
button {
	color: v-bind('props.primary');
	border-color: v-bind('props.primary');
}

button:focus {
	--tw-ring-color: v-bind('props.primary');
	box-shadow: var(--tw-ring-inset) 0 0 0 calc(2px + var(--tw-ring-offset-width)) var(--tw-ring-color);
	outline: 2px solid transparent;
	outline-offset: 2px;
	--tw-ring-offset-width: 2px;
	box-shadow: 0 0 0 var(--tw-ring-offset-width) var(--tw-ring-offset-color), var(--tw-ring-shadow);
}

button:hover {
	background: v-bind('props.primary');
	color: v-bind('props.secondary');
	opacity: 90%;
}
</style>