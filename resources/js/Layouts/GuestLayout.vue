<template>
    <div
        class="flex min-h-screen flex-col items-center justify-center bg-gray-100 py-2 sm:py-0 relative overflow-hidden"
    >
        <!-- Background Image -->
        <img src="/img/bg.png" alt="Background" class="absolute inset-0 w-full h-full object-cover opacity-70 pointer-events-none" />

        <div
            class="relative z-10 w-full max-w-md rounded-2xl bg-white p-8 shadow-xl ring-1 ring-gray-200"
        >
            <slot />
        </div>
    </div>
</template>
