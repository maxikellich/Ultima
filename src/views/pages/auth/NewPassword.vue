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
                        <i class="pi pi-key text-primary text-4xl"></i>
                    </div>
                    <div class="mt-4">
                        <h1 class="m-0 text-primary font-semibold text-4xl">Choose your new password!</h1>
                        <span class="block text-700 mt-2">Enter your new password</span>
                    </div>
                </div>
                <div class="flex flex-column gap-3 mt-6">
                    <div class="p-inputgroup">
                        <span class="p-inputgroup-addon"><i class="pi pi-key"></i></span>
                        <Password id="password" placeholder="Password" inputClass="w-full" toggleMask></Password>
                    </div>
                    <div class="p-inputgroup">
                        <span class="p-inputgroup-addon"><i class="pi pi-key z-2"></i></span>
                        <Password id="password" placeholder="Repeat Password" inputClass="w-full" toggleMask></Password>
                    </div>
                    <div class="p-inputgroup">
                        <Button v-ripple class="w-full" label="SAVE NEW PASSWORD"></Button>
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
