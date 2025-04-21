<template>
    <section v-if="pending">Loading...</section>
    <section v-else-if="error">Something went wrong  :-(</section>
    <section v-else>
        Here are the repos:
        <ul class="grid grid-cols-1 gap-4">
            <li v-for="repository in repos" :key="repository.id" class="border border-gray-200 dark:border-gray-800 rounded-sm p-4 hover:bg-gray-100 font-mono dark:hover:bg-gray-800">
                <a :href="repository.html_url" target="_blank">
                    <div class="flex items-center justify-between text-sm">
                        <div class="font-semibold">{{ repository.name }}</div>
                        <div>{{ repository.stargazers_count }} *</div>
                    </div>
                    <p class="text-sm">
                        {{ repository.description }}
                    </p>
                </a>
            </li>
        </ul>
        </section>
</template>

<script setup>
    const {error, pending, data} = await useFetch('https://api.github.com/users/RichardCochrane/repos')
    const repos = computed(
        () => data.value.filter(repo => repo.description).sort(a => a.name)
    )
</script>
