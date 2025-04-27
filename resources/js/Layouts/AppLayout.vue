<script setup>
import Sidebar from "@/Layouts/Sidebar.vue";
import Navbar from "@/Layouts/Navbar.vue";
import Footer from "@/Layouts/Footer.vue";
import { ref } from "vue";

const sidebarOpen = ref(false);
</script>

<template>
    <div class="min-h-screen bg-gray-50 flex">
        <!-- Mobile sidebar backdrop -->
        <div
            v-if="sidebarOpen"
            class="fixed inset-0 bg-gray-900 bg-opacity-50 z-40 md:hidden"
            @click="sidebarOpen = false"
        ></div>

        <!-- Sidebar -->
        <Sidebar
            :sidebarOpen="sidebarOpen"
            @close-sidebar="sidebarOpen = false"
        />

        <div class="flex-1 flex flex-col overflow-hidden">
            <!-- Navbar -->
            <Navbar @toggle-sidebar="sidebarOpen = !sidebarOpen" />

            <!-- Main Content -->
            <main class="flex-1 overflow-y-auto p-4 md:p-6 bg-gray-50">
                <div class="max-w-7xl mx-auto">
                    <slot />
                </div>
            </main>

            <!-- Footer -->
            <Footer />
        </div>
    </div>
</template>
