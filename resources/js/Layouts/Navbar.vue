<script setup>
defineProps({
    user: {
        type: Object,
        default: null,
    },
});

const emit = defineEmits(["toggle-sidebar"]);
</script>

<template>
    <header class="bg-white shadow-sm">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex justify-between h-16">
                <!-- Left section (hamburger and logo) -->
                <div class="flex items-center">
                    <!-- Mobile menu button -->
                    <button
                        @click="emit('toggle-sidebar')"
                        class="md:hidden p-2 rounded-md text-gray-500 hover:text-gray-600 hover:bg-gray-100 focus:outline-none"
                    >
                        <svg
                            class="h-6 w-6"
                            fill="none"
                            viewBox="0 0 24 24"
                            stroke="currentColor"
                        >
                            <path
                                stroke-linecap="round"
                                stroke-linejoin="round"
                                stroke-width="2"
                                d="M4 6h16M4 12h16M4 18h16"
                            />
                        </svg>
                    </button>

                    <!-- Logo - Hidden on mobile -->
                    <div class="hidden md:flex items-center ml-4">
                        <svg
                            class="h-8 w-8 text-indigo-600"
                            fill="none"
                            viewBox="0 0 24 24"
                            stroke="currentColor"
                        >
                            <path
                                stroke-linecap="round"
                                stroke-linejoin="round"
                                stroke-width="2"
                                d="M9 12l2 2 4-4m5.618-4.016A11.955 11.955 0 0112 2.944a11.955 11.955 0 01-8.618 3.04A12.02 12.02 0 003 9c0 5.591 3.824 10.29 9 11.622 5.176-1.332 9-6.03 9-11.622 0-1.042-.133-2.052-.382-3.016z"
                            />
                        </svg>
                        <span class="ml-2 text-xl font-bold text-gray-800"
                            >Pifacia</span
                        >
                    </div>
                </div>

                <!-- Right section (user profile) -->
                <div class="flex items-center">
                    <div class="ml-4 flex items-center md:ml-6">
                        <!-- Profile dropdown -->
                        <div class="ml-3 relative">
                            <div class="flex items-center">
                                <span
                                    class="mr-2 text-sm font-medium text-gray-700 hidden md:inline"
                                    >{{ user?.name }}</span
                                >
                                <button
                                    class="max-w-xs flex items-center text-sm rounded-full focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-indigo-500"
                                >
                                    <span class="sr-only">Open user menu</span>
                                    <img
                                        class="h-8 w-8 rounded-full"
                                        src="/img/profile.png"
                                        alt="Profile"
                                    />
                                </button>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </header>
</template>
