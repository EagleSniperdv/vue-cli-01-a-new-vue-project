<template>
    <li>
        <h2>{{ name }}</h2>
        <button @click="toggleDetails">{{ detailsAreVisible ? 'Hide' : 'Show' }} Details</button>
        <ul v-if="detailsAreVisible">
            <li><strong>Phone:</strong>{{ phoneNumber }}</li>
            <li><strong>Email:</strong>{{ emailAddress }}</li>
            <li>{{ id }}</li>
            
        </ul>
        <button @click="$emit('delete', id)">DELETE</button>
    </li>
</template>

<script>
export default {
    props: [
        'id',
        'name',
        'phoneNumber',
        'emailAddress'
    ],

    emits: ['delete'],
    data() {
        return {
            detailsAreVisible: false,
        }
    },

    methods:{
        toggleDetails() {
            this.detailsAreVisible = !this.detailsAreVisible;
        },
        
    }
};
</script>

