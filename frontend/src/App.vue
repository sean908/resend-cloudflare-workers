<script setup lang="ts">
import { ref } from 'vue';
import EmailForm from './components/EmailForm.vue';

const appName = 'Resend Online';
</script>

<template>
  <div class="min-h-screen bg-gray-50">
    <header class="bg-white shadow-sm">
      <div class="max-w-4xl mx-auto px-4 py-6">
        <h1 class="text-3xl font-bold text-gray-900">{{ appName }}</h1>
        <p class="text-gray-600 mt-2">基于 Resend API 的在线邮件发送工具</p>
      </div>
    </header>

    <main class="max-w-4xl mx-auto px-4 py-8">
      <EmailForm />
    </main>

    <footer class="mt-16 py-8 text-center text-gray-500 text-sm">
      <p>Powered by Resend API & Cloudflare Workers</p>
    </footer>
  </div>
</template>
