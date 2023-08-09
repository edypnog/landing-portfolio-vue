
<template>

    <div class="bg-white shadow-md rounded-md p-4" v-if="project.language">
        <div class="flex items-center justify-between">
            <h2 class="text-lg font-semibold">{{ project.title }}</h2>
            <a :href="project.link" target="_blank" class="text-blue-500">View on GitHub</a>
            </div>
            <p class="mt-2 w-100 text-gray-500 p-1">{{ project.description }}</p>
            <p class="mt-2 w-1/3 text-gray-light font-bold bg-darkblue p-1">{{ project.language }}</p>
            <div class="mt-4">
        </div>
    </div>
</template>

<script>
export default {
  props: {
    project: {
      type: Object,
      required: true
    }
  },
  data() {
    return {
      isExpanded: false // Example data property
    };
  },
  methods: {
    toggleExpand() {
      this.isExpanded = !this.isExpanded;
    }
  }
};
</script>


<style scoped>
.portfolio-card {
border: 1px solid #e2e8f0;
border-radius: 8px;
overflow: hidden;
box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

.card-image img {
width: 100%;
height: auto;
}

.card-content {
padding: 1rem;
}

.text-lg {
font-size: 1.125rem;
}

.text-gray-500 {
color: #718096;
}

.text-blue-500 {
color: #4299e1;
}
</style>
