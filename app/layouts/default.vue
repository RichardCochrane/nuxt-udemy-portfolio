<template>
    <div class="container mx-auto max-w-2xl">
        <header class="flex justify-between items-center mt-5">
            <div>
                <NuxtLink to="/" class="text-xl font-semibold p-2 hover:bg-gray-200">Screamer</NuxtLink>
            </div>
            <Menu />
        </header>
        <main class="p-2 mt-10">
            <slot />
        </main>
    </div>
</template>

<script setup>
    useSeoMeta({
        title: 'Rich Test',
        description: '[description]',
        ogTitle: '[og:title]',
        ogDescription: '[og:description]',
        ogImage: '[og:image]',
        ogUrl: '[og:url]',
        twitterTitle: '[twitter:title]',
        twitterDescription: '[twitter:description]',
        twitterImage: '[twitter:image]',
        twitterCard: 'summary'
    })

    useHead({
        htmlAttrs: {
            lang: 'en'
        },
        link: [
            {
            rel: 'icon',
            type: 'image/png',
            href: '/favicon.png'
            }
        ],
        titleTemplate: '%s - Rich',
        link: [
            {
            rel: 'preconnect',
            href: 'https://fonts.googleapis.com'
            },
            {
            rel: 'stylesheet',
            href: 'https://fonts.googleapis.com/css2?family=Roboto&display=swap',
            crossorigin: ''
            }
        ]
    })
</script>

<style>
body {
    font-family: roboto;
}
</style>
