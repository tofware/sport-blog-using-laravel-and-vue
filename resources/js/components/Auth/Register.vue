<template>
    <form @submit.prevent="submitRegister">
        <!-- Name -->
        <div>
            <label for="name" class="block font-medium text-sm text-gray-700">
                Name
            </label>
            <input v-model="registerForm.name" id="name" type="text"
                   class="block mt-1 w-full rounded-md shadow-sm border-gray-300 focus:border-indigo-300 focus:ring focus:ring-indigo-200 focus:ring-opacity-50"
                   required autofocus autocomplete="username">
            <!-- Validation Errors -->
            <div class="text-red-600 mt-1">
                <div v-for="message in validationErrors?.name">
                    {{ message }}
                </div>
            </div>
        </div>

        <!-- Email -->
        <div>
            <label for="email" class="block font-medium text-sm text-gray-700">
                Email
            </label>
            <input v-model="registerForm.email" id="email" type="email"
                   class="block mt-1 w-full rounded-md shadow-sm border-gray-300 focus:border-indigo-300 focus:ring focus:ring-indigo-200 focus:ring-opacity-50"
                   required autofocus autocomplete="username">
            <!-- Validation Errors -->
            <div class="text-red-600 mt-1">
                <div v-for="message in validationErrors?.email">
                    {{ message }}
                </div>
            </div>
        </div>

        <!-- Password -->
        <div class="mt-4">
            <label for="password" class="block font-medium text-sm text-gray-700">
                Password
            </label>
            <input v-model="registerForm.password" id="password" type="password"
                   class="block mt-1 w-full rounded-md shadow-sm border-gray-300 focus:border-indigo-300 focus:ring focus:ring-indigo-200 focus:ring-opacity-50"
                   required autocomplete="current-password">
            <!-- Validation Errors -->
            <div class="text-red-600 mt-1">
                <div v-for="message in validationErrors?.password">
                    {{ message }}
                </div>
            </div>
        </div>

        <!-- Confirm Password -->
        <div class="mt-4">
            <label for="confirm_password" class="block font-medium text-sm text-gray-700">
                Password
            </label>
            <input v-model="registerForm.password_confirmation" id="confirm_password" type="password"
                   class="block mt-1 w-full rounded-md shadow-sm border-gray-300 focus:border-indigo-300 focus:ring focus:ring-indigo-200 focus:ring-opacity-50"
                   required autocomplete="current-password">
            <!-- Validation Errors -->
            <div class="text-red-600 mt-1">
                <div v-for="message in validationErrors?.password_confirmation">
                    {{ message }}
                </div>
            </div>
        </div>

        <!-- Buttons -->
        <div class="flex items-center justify-end mt-4">
            <button
                class="inline-flex items-center px-4 py-2 bg-gray-800 border border-transparent rounded-md font-semibold text-xs text-white uppercase tracking-widest hover:bg-gray-700 active:bg-gray-900 focus:outline-none focus:border-gray-900 focus:shadow-outline-gray transition ease-in-out duration-150 ml-4"
                :class="{ 'opacity-25': processing }"
                :disabled="processing"
            >
                Register
            </button>
        </div>
    </form>
</template>

<script setup>
import useAuth from '@/composables/auth';

const {registerForm, validationErrors, processing, submitRegister} = useAuth()
</script>
