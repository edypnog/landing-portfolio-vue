<template>
    <div class=" bg-gray-100 my-8">

        <!-- About Me Section -->
        <div class="max-w-6xl mx-auto px-4 sm:px-6 lg:px-8 flex flex-col md:flex-row">

            <!-- Left Column: Text Presentation -->
            <div class="md:w-1/2 md:pr-8 mb-8 md:mb-0">
                <h1 class="text-3xl font-semibold mb-4">console.log('about me');</h1>
                <p class="text-gray-600">
                    Hey there! 🏖️ I'm based in Brazil and I'm passionate about web and mobile development. I've taken the exciting journey of self-study to dive deep into the world of coding. When I'm not crafting digital experiences, you might find me exploring new coffee spots or learning a new thing. Let's connect and share our coding adventures! 🚀🌟
                </p>
            </div>

            <!-- Right Column: Picture -->
            <div class="md:w-1/2 flex justify-center">
                <div class="w-60 h-60 bg-gray-300 rounded-full flex items-center justify-center">
                    <img src="../assets/cat.svg" alt="Your Profile" class="w-60 h-60 rounded-full">
                </div>
            </div>

        </div>

        <!-- Button to Open Modal -->
        <div class="flex justify-center mt-8">
            <button @click="openModal" class="bg-blue-500 text-white px-4 py-2 rounded-lg shadow-md hover:bg-blue-600">
                View Technologies
            </button>
        </div>

        <!-- Modal -->
        <div v-if="isModalOpen" class="inset-0 flex items-center justify-center bg-black bg-opacity-50"
            @click="closeModal">
            <div class="bg-white w-2/3 md:w-1/3 p-4 rounded-lg shadow-lg" @click.stop>
                <h2 class="text-xl font-semibold mb-4">Technologies I Use</h2>
                <ul class="list-disc pl-6">
                    <li>Vue.js</li>
                    <li>Python</li>
                    <li>Django</li>
                    <li>Flask</li>
                    <li>React</li>
                    <li>Flutter</li>
                    <li>Tailwind</li>
                    <!-- Add more technologies here -->
                </ul>
                <button @click="closeModal"
                    class="mt-4 bg-blue-500 text-white px-4 py-2 rounded-lg shadow-md hover:bg-blue-600">
                    Close
                </button>
            </div>
        </div>
    </div>
</template>  

<script>
export default {
    data() {
        return {
            isModalOpen: false
        };
    },
    methods: {
        openModal() {
            this.isModalOpen = true;
        },
        closeModal() {
            this.isModalOpen = false;
        }
    }
};



</script>