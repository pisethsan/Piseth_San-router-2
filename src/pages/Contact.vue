<template>
  <main>
    <div class="max-w-md mx-auto mt-10 p-6 bg-white rounded-2xl shadow-md">
        <h2 class="font-moul text-xl font-bold text-gray-900 sm:text-3xl">
            {{ $t('contact_me') }}
        </h2>
        <p class="text-gray-900 mb-8">{{ $t('contact_des') }}</p>
        <Form name="ask-question"
    method="post"
    data-netlify="true"
    data-netlify-honeypot="bot-field" :validation-schema="validationSchema" @submit="handleSubmit" class="space-y-4">
            <!-- Name Field -->
            <div>
                <label class="block mb-1 text-sm font-medium text-gray-700">
                    {{ $t('name') }}
                </label>
                <Field name="name" type="text" v-model="form.name"
                    class="w-full px-4 py-2 border border-gray-300 rounded-xl focus:outline-none focus:ring-2 focus:ring-blue-500"
                    :placeholder="$t('enter_your_name') " />
                <ErrorMessage name="name" class="text-red-600 text-sm mt-1" />
            </div>

            <!-- Email Field -->
            <div>
                <label class="block mb-1 text-sm font-medium text-gray-700">
                    {{ $t('email') }}
                </label>
                <Field name="email" type="email" v-model="form.email"
                    class="w-full px-4 py-2 border border-gray-300 rounded-xl focus:outline-none focus:ring-2 focus:ring-blue-500"
                    :placeholder="$t('enter_your_email') "/>
                <ErrorMessage name="email" class="text-red-600 text-sm mt-1" />
            </div>

            <!-- Message Field -->
            <div>
                <label class="block text-sm font-medium text-gray-900 mb-2">
                    {{ $t('message') }}
                </label>
                <Field as="textarea" name="message" v-model="form.message" rows="5"
                    class="w-full px-4 py-2 border border-gray-300 rounded-xl focus:outline-none focus:ring-2 focus:ring-blue-500"
                    :placeholder="$t('enter_your_message') " />
                <ErrorMessage name="message" class="text-red-600 text-sm mt-1" />   
            </div>

            <!-- Send Button -->
            <button
          type="submit"
          :disabled="isLoading"
          class="w-full py-2 bg-blue-600 text-white font-semibold rounded-xl hover:bg-blue-700 transition duration-200 flex items-center justify-center"
        >
          <span v-if="isLoading" class="flex items-center">
            <svg class="animate-spin -ml-1 mr-3 h-5 w-5 text-white" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24">
              <circle class="opacity-25" cx="12" cy="12" r="10" stroke="currentColor" stroke-width="4"></circle>
              <path class="opacity-75" fill="currentColor" d="M4 12a8 8 0 018-8V0C5.373 0 0 5.373 0 12h4zm2 5.291A7.962 7.962 0 014 12H0c0 3.042 1.135 5.824 3 7.938l3-2.647z"></path>
            </svg>
            {{ $t('Sending...') }}
          </span>
          <span v-else>{{ $t('Send') }}</span>
        </button>
        </Form>
    </div>
    <!-- Contact Info Section -->
    <div class="mx-auto max-w-md px-4 py-8 sm:px-6 lg:px-8">
      <div class="space-y-6">
        <!-- Phone -->
        <div class="flex items-center gap-4">
          <div class="flex h-12 w-12 shrink-0 items-center justify-center rounded-full bg-indigo-100 text-indigo-600">
            <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
              <path stroke-linecap="round" stroke-linejoin="round" d="M3 5a2 2 0 012-2h3.28a1 1 0 01.948.684l1.498 4.493a1 1 0 01-.502 1.21l-2.257 1.13a11.042 11.042 0 005.516 5.516l1.13-2.257a1 1 0 011.21-.502l4.493 1.498a1 1 0 01.684.949V19a2 2 0 01-2 2h-1C9.716 21 3 14.284 3 6V5z" />
            </svg>
          </div>
          <div>
            <h4 class="text-lg font-semibold text-gray-800">070 21 55 57</h4>
          </div>
        </div>
        <!-- Email -->
        <div class="flex items-center gap-4">
          <div class="flex h-12 w-12 shrink-0 items-center justify-center rounded-full bg-indigo-100 text-indigo-600">
            <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
              <path stroke-linecap="round" stroke-linejoin="round" d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z" />
            </svg>
          </div>
          <div>
            <h4 class="text-lg font-semibold text-gray-800">pisethsan67167@gmail.com</h4>
          </div>
        </div>
        <!-- Address -->
        <div class="flex items-center gap-4">
          <div class="flex h-12 w-12 shrink-0 items-center justify-center rounded-full bg-indigo-100 text-indigo-600">
            <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
              <path stroke-linecap="round" stroke-linejoin="round" d="M17.657 16.657L13.414 20.9a1.998 1.998 0 01-2.827 0l-4.244-4.243a8 8 0 1111.314 0z" />
              <path stroke-linecap="round" stroke-linejoin="round" d="M15 11a3 3 0 11-6 0 3 3 0 016 0z" />
            </svg>
          </div>
          <div>
            <h4 class="text-lg font-semibold text-gray-800">Tbong Khmum</h4>
          </div>
        </div>
      </div>
    </div>
  </main>
</template>

<script>
import axios from 'axios';
import { Form, Field, ErrorMessage } from 'vee-validate';
import * as yup from 'yup';

export default {
    name: 'ContactForm',
    components: {
        Form,
        Field,
        ErrorMessage
    },
    data() {
        return {
            form: {
                name: '',
                email: '',
                message: ''
            },
            isLoading: false, // Added loading state
            successMessage: '', // Added success message state
            errorMessage: '', // Added error message state

            validationSchema: yup.object(
                {
                    name: yup.string().matches(/^[A-Za-z\s]+$/,
                        'Only alphabet and space is accepted'
                    )
                        .min(3, 'Name must be at least 3 characters')
                        .required('Name is required'),
                    email: yup.string().email('Invalid email').required('Email is required'),
                    message: yup.string().required('Message is required').min(3, 'Message must be at least 3 characters.'),
                })
        }
    },
    methods: {
        async handleSubmit() {
            console.log('Form submitted:', this.form)
            // Reset messages
            this.successMessage = '';
            this.errorMessage = '';

            // Set loading to true
            this.isLoading = true;
            // You can add validation or API calls here
            try {
                const response = await axios.post(`${import.meta.env.VITE_USER_API}/api/v1/contact`, {
                    name: this.form.name,
                    email: this.form.email,
                    message: this.form.message
                })
                console.log('Form submitted successfully:', response.data);
                this.form = {
                    name: '',
                    email: '',
                    message: ''
                };
                alert('Your message has been submitted successfully!');
                this.$router.push('/contact');
            } catch (error) {
                console.error('Error submitting form:', error);
                alert('There was an error submitting your message. Please try again.');
            } finally {
                this.isLoading = false;
            }
        }
    }
}
</script>