<template>
	<div class="px-4 py-5 bg-white space-y-6 sm:p-6">
		<fieldset>
			<legend class="sr-only">By Email</legend>
			<div class="text-base font-medium text-gray-900" aria-hidden="true">By Email</div>
			<div class="mt-4 space-y-4">
				<div class="flex items-start">
					<div class="flex items-center h-5">
						<input id="comments" name="comments" type="checkbox" class="h-4 w-4 border-gray-300 rounded" checked />
					</div>
					<div class="ml-3 text-sm">
						<label for="comments" class="font-medium text-gray-700">Comments</label>
						<p class="text-gray-500">Get notified when someones posts a comment on a posting.</p>
					</div>
				</div>
				<div class="flex items-start">
					<div class="flex items-center h-5">
						<input id="candidates" name="candidates" type="checkbox" class="h-4 w-4 border-gray-300 rounded" />
					</div>
					<div class="ml-3 text-sm">
						<label for="candidates" class="font-medium text-gray-700">Candidates</label>
						<p class="text-gray-500">Get notified when a candidate applies for a job.</p>
					</div>
				</div>
				<div class="flex items-start">
					<div class="flex items-center h-5">
						<input id="offers" name="offers" type="checkbox" class="h-4 w-4 border-gray-300 rounded" />
					</div>
					<div class="ml-3 text-sm">
						<label for="offers" class="font-medium text-gray-700">Offers</label>
						<p class="text-gray-500">Get notified when a candidate accepts or rejects an offer.</p>
					</div>
				</div>
			</div>
		</fieldset>
		<fieldset>
			<legend class="contents text-base font-medium text-gray-900">Push Notifications</legend>
			<p class="text-sm text-gray-500">These are delivered via SMS to your mobile phone.</p>
			<div class="mt-4 space-y-4">
				<div class="flex items-center">
					<input id="push-everything" name="push-notifications" type="radio" class="h-4 w-4 border-gray-300" checked />
					<label for="push-everything" class="ml-3 block text-sm font-medium text-gray-700"> Everything </label>
				</div>
				<div class="flex items-center">
					<input id="push-email" name="push-notifications" type="radio" class="h-4 w-4 border-gray-300" />
					<label for="push-email" class="ml-3 block text-sm font-medium text-gray-700"> Same as email </label>
				</div>
				<div class="flex items-center">
					<input id="push-nothing" name="push-notifications" type="radio" class="h-4 w-4 border-gray-300" />
					<label for="push-nothing" class="ml-3 block text-sm font-medium text-gray-700"> No push notifications </label>
				</div>
			</div>
		</fieldset>
	</div>
</template>

<script setup>
import { reactive } from "@vue/reactivity"

const props = defineProps(['primary', 'secondary'])

</script>
<style scoped>
[type=checkbox]:checked, [type=radio]:checked {
	color: v-bind('props.primary');
}

[type=checkbox]:focus, [type=radio]:focus {
	--tw-ring-color: v-bind('props.primary');
	box-shadow: var(--tw-ring-inset) 0 0 0 calc(2px + var(--tw-ring-offset-width)) var(--tw-ring-color);
	outline: 2px solid transparent;
	outline-offset: 2px;
	--tw-ring-offset-width: 2px;
	box-shadow: 0 0 0 var(--tw-ring-offset-width) var(--tw-ring-offset-color), var(--tw-ring-shadow);
}
</style>