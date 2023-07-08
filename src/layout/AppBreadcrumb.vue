<script setup>
import { ref, watch } from 'vue';
import { useRoute } from 'vue-router';

const home = { icon: 'pi pi-home', to: '/' };
const items = ref([]);

const route = useRoute();

watch(
    route,
    () => {
        watchRouter();
    },
    { immediate: true }
);

function watchRouter() {
    if (route.meta.breadcrumb) {
        items.value = [];
        const bc = route.meta.breadcrumb[0];
        for (let pro in bc) {
            items.value.push({ label: bc[pro] });
        }
    }
}
</script>
<template>
    <div class="layout-breadcrumb-container">
        <nav class="layout-breadcrumb">
            <ol>
                <li>
                    <router-link :to="home.to" style="color: inherit">
                        <i :class="home.icon"></i>
                    </router-link>
                </li>
                <li v-for="(item, index) in items" :key="index">
                    <i class="pi pi-angle-right"></i>
                    <span>{{ item.label }}</span>
                </li>
            </ol>
        </nav>

        <div class="layout-breadcrumb-buttons">
            <Button icon="pi pi-cloud-upload" class="p-button-rounded p-button-text p-button-plain"></Button>
            <Button icon="pi pi-bookmark" class="p-button-rounded p-button-text p-button-plain"></Button>
            <Button icon="pi pi-power-off" class="p-button-rounded p-button-text p-button-plain"></Button>
        </div>
    </div>
</template>
