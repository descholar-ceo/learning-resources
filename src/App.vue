<template>
    <ul>
        <learning-resources
            v-for="res in storedResources" 
            :key="res.id"
            :title="res.title"
            :description="res.description"
            :link="res.link"
        ></learning-resources>
    </ul>
</template>

<script>
import LearningResources from './components/learning-resources/ResourceItem.vue';
export default{
    components: {
        LearningResources,
    },
    data() {
        return {
            storedResources: [
                {
                    id: 'official-guide',
                    title: 'Official Guide',
                    description: 'The official guide is documentation',
                    link: 'https://vuejs.org'
                },
                {
                    id: 'google',
                    title: 'Google',
                    description: 'You need to learn to google ...',
                    link: 'https://google.com'
                },
            ]
        }
    },
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap');

* {
  box-sizing: border-box;
}

html {
  font-family: 'Roboto', sans-serif;
}

body {
  margin: 0;
}
</style>
