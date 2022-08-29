<template>
	<span class="inline-flex justify-center py-1 px-3 border shadow-sm text-xs font-bold leading-4 rounded-full focus:outline-none focus:ring-2 focus:ring-offset-2 transition-opacity duration-300 ease-in-out hover:cursor-default">{{ label }}</span>
</template>

<script setup>
import { reactive } from "@vue/reactivity"

const props = defineProps(['primary', 'secondary', 'label'])

</script>
<style scoped>
span {
	background: v-bind('props.secondary');
	color: v-bind('props.primary');
	border-color: v-bind('props.primary');
}

span:hover {
	opacity: 85%;
}
</style>