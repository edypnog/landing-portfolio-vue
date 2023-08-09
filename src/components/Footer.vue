<template>
    <footer class="text-center text-gray-500 mt-8 mb-8">
        Created with ❤️ by <a href="https://github.com/edypnog" class="underline" target="_blank" > Edy Nogueira</a>
        &copy; {{ currentYear }}
    </footer>
</template>


<script>
export default {
    data() {
        return {
            currentYear: new Date().getFullYear()
        }
    },
}

</script>