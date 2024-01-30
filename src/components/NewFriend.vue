<template>
    <form @submit.prevent="submitData">
        <div>
            <label for="">Name</label>
            <input type="text" v-model="enteredName">
        </div>
        <div>
            <label for="">Phone</label>
            <input type="tel" v-model="enteredPhone">
        </div>
        <div>
            <label for="">E-mail</label>
            <input type="text" v-model="enteredEmail">
        </div>
        <div>
            <label for="">ID</label>
            <input type="text" v-model="enteredId">
        </div>
        <div>
            <button id="btn">Add contact</button>
        </div>
    </form>
</template>

<script>
export default{
    emits:['add-contact'],
    data() {
        return {
            enteredName:'',
            enteredPhone: '',
            enteredEmail: '',
            enteredId: ''
        }
    },

    methods: {
        submitData() {
            this.$emit(
                'add-contact',
                this.enteredName,
                this.enteredPhone,
                this.enteredEmail,
                this.enteredId
            )
        }
    }
}
</script>

<style>
#btn {
    margin: 1.5rem;
}
</style>

