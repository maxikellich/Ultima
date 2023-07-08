<script setup>
import { useLayout } from '@/layout/composables/layout';
const { layoutConfig } = useLayout();
</script>
<template>
    <div class="layout-footer">
        <img :src="'/layout/images/logo/footer-' + (layoutConfig.colorScheme.value === 'light' ? 'ultima' : 'ultima-dark') + '.svg'" alt="ultima-footer-logo" />
        <div class="flex gap-2">
            <Button v-ripple icon="pi pi-github" class="p-button-rounded p-button-text p-button-plain"></Button>
            <Button v-ripple icon="pi pi-facebook" class="p-button-rounded p-button-text p-button-plain"></Button>
            <Button v-ripple icon="pi pi-twitter" class="p-button-rounded p-button-text p-button-plain"></Button>
        </div>
    </div>
</template>
