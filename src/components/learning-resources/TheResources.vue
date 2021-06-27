<template>
    <base-card>
        <base-button @click="setSelectedTab('stored-resources')" :mode="storedResButtonMode">Stored resources</base-button>
        <base-button @click="setSelectedTab('add-resource')" :mode="addResButtonMode">Add resource</base-button>
    </base-card>
    <component :is="selectedTab"></component>
</template>

<script>
import StoredResources from './StoredResources.vue';
import AddResource from './AddResource.vue';
export default {
    components: {
        StoredResources,
        AddResource
    },
    data(){
        return{
            selectedTab: 'stored-resources',
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
    provide(){
        return {
            resources: this.storedResources,
            addResource: this.addResource
        }
    },
    computed: {
        storedResButtonMode(){
            return this.selectedTab === 'stored-resources' ? null : 'flat';
        },
        addResButtonMode(){
            return this.selectedTab === 'add-resource' ? null : 'flat';
        }
    },
    methods: {
        setSelectedTab(tab){
            this.selectedTab = tab;
        },
        addResource(title, description, url){
            const newResource = {
                id: new Date().toISOString(),
                title,
                description,
                link: url
            }
            this.storedResources.unshift(newResource);
            this.selectedTab = 'stored-resources'
        }
    }
}
</script>