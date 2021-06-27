<template>
    <ul></ul>
</template>

<script>
export default{
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
