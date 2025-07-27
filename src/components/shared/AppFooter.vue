<script>
import feather from 'feather-icons';
import FooterCopyright from './FooterCopyright.vue';
import { socialLinks } from '../../data/socialLinks';

export default {
	components: { FooterCopyright },
	data() {
		return {
			socials: socialLinks,
			form: {
				name: '',
				email: '',
				message: '',
			},
		};
	},
	mounted() {
		feather.replace();
	},
	updated() {
		feather.replace();
	},
	methods: {
		submitForm() {
			// You can handle form submission here (e.g., send to API or show a message)
			alert('Thank you for contacting me!');
			this.form.name = '';
			this.form.email = '';
			this.form.message = '';
		},
	},
};
</script>

<template>
	<div class="container mx-auto">
		<div class="pt-20 sm:pt-30 pb-8 mt-20 border-t-2 border-primary-light dark:border-secondary-dark">
			<!-- Footer contact form -->
			<div class="flex flex-col justify-center items-center mb-12 sm:mb-20">
				<p
					class="font-general-semibold text-3xl sm:text-4xl font-semibold text-primary-dark dark:text-primary-light mb-5">
					Contact Me
				</p>
				<form @submit.prevent="submitForm"
					class="w-full max-w-md bg-gray-50 dark:bg-ternary-dark p-8 rounded-xl shadow-lg border border-gray-200 dark:border-gray-700 space-y-6">
					<div>
						<label class="block text-gray-700 dark:text-gray-300 mb-2 font-semibold" for="name">Name</label>
						<input v-model="form.name" type="text" id="name"
							class="w-full p-3 border border-gray-300 dark:border-gray-600 rounded-lg focus:outline-none focus:ring-2 focus:ring-indigo-400 dark:bg-secondary-dark dark:text-white transition"
							placeholder="Your name" required />
					</div>
					<div>
						<label class="block text-gray-700 dark:text-gray-300 mb-2 font-semibold"
							for="email">Email</label>
						<input v-model="form.email" type="email" id="email"
							class="w-full p-3 border border-gray-300 dark:border-gray-600 rounded-lg focus:outline-none focus:ring-2 focus:ring-indigo-400 dark:bg-secondary-dark dark:text-white transition"
							placeholder="you@email.com" required />
					</div>
					<div>
						<label class="block text-gray-700 dark:text-gray-300 mb-2 font-semibold"
							for="message">Message</label>
						<textarea v-model="form.message" id="message"
							class="w-full p-3 border border-gray-300 dark:border-gray-600 rounded-lg focus:outline-none focus:ring-2 focus:ring-indigo-400 dark:bg-secondary-dark dark:text-white transition"
							rows="4" placeholder="Type your message..." required></textarea>
					</div>
					<button type="submit"
						class="w-full bg-indigo-500 hover:bg-indigo-600 text-white py-3 px-4 rounded-lg font-semibold shadow transition duration-300">
						Send
					</button>
				</form>
				<!-- Social buttons -->
				<div class="flex gap-4 mt-8">
					<a v-for="social in socials" :key="social.name" :href="social.url" target="_blank" rel="noopener"
						class="p-3 rounded-full bg-green-100 dark:bg-secondary-dark shadow-lg hover:bg-indigo-500 hover:text-white transition duration-300 ease-in-out transform hover:-translate-y-1 hover:scale-110 border border-gray-200 dark:border-gray-700 flex items-center justify-center"
						:style="{ color: '#d1fae5' }">
						<i :data-feather="social.icon" class="w-6 h-6"></i>
					</a>
				</div>
			</div>
			<!-- Footer copyright -->
			<FooterCopyright />
		</div>
	</div>
</template>

<style scoped></style>
