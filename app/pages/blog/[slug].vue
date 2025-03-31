<template>
    <div>
        We are inside a blog.<br><br>
        Post ID is {{ route.params.slug }}
    </div>
</template>

<script setup>
    const route = useRoute()
</script>
