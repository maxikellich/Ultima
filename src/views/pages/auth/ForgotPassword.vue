<script setup>
import { ref } from 'vue';
import AppConfig from '@/layout/AppConfig.vue';

const backgroundImage = ref('url(/layout/images/pages/accessDenied-bg.jpg)');
const backgroundStyle = ref({
    background: backgroundImage.value,
});
</script>

<template>
    <div class="h-screen flex w-full surface-ground">
        <div class="flex flex-1 flex-column surface-ground align-items-center justify-content-center">
            <div class="w-11 sm:w-30rem">
                <div class="flex flex-column">
                    <div style="height: 56px; width: 56px" class="bg-primary-50 border-circle flex align-items-center justify-content-center">
                        <i class="pi pi-question text-primary text-4xl"></i>
                    </div>
                    <div class="mt-4">
                        <h1 class="m-0 text-primary font-semibold text-4xl">Forgot password?</h1>
                        <span class="block text-700 mt-2">Please enter your email address</span>
                    </div>
                </div>
                <div class="flex flex-column gap-3 mt-6">
                    <div class="p-inputgroup">
                        <span class="p-inputgroup-addon"><i class="pi pi-at"></i></span>
                        <InputText placeholder="Email" />
                    </div>
                    <div class="p-inputgroup">
                        <Button v-ripple class="w-full" label="SUBMIT EMAIL"></Button>
                    </div>
                    <div class="p-inputgroup">
                        <Button v-ripple class="w-full p-button-text text-primary-500" label="BACK TO LOGIN"></Button>
                    </div>
                </div>
            </div>
        </div>
        <div :style="backgroundStyle" class="hidden lg:flex flex-1 align-items-center justify-content-center bg-cover">
            <img src="/layout/images/logo/vector_logo.png" alt="" />
        </div>
    </div>
    <AppConfig simple />
</template>
