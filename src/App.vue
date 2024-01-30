<template>
    <section>
        <header>
            <h1>My Friends</h1>
        </header>
        <ul>
            <friend-contact
            v-for="friend in friends"
            :key="friend.id"
            :id="friend.id"
            :name='friend.name'
            :phone-number='friend.phone'
            :email-address='friend.email'
            ></friend-contact>
        </ul>
</section>
</template>

<script>

export default {

    data() {
        return {
            friends: [
  {
    id: 'manuel',
    name: 'Manuel Lorenzo',
    phone: '07861556712',
    email: '@manuelgmail.com'
  },
  {
    id: 'manu',
    name: 'Manu Lorenzo',
    phone: '0786588496712',
    email: '@manugmail.com'
  },
  {
    id: 'julie',
    name: 'Julie Lorenzo',
    phone: '012345671',
    email: '@juliegmail.com'
  },
  {
    id: 'john',
    name: 'John Doe',
    phone: '9876543210',
    email: '@johndoe.com'
  },
  {
    id: 'alice',
    name: 'Alice Smith',
    phone: '5551234567',
    email: '@alicegmail.com'
  },
  {
    id: 'bob',
    name: 'Bob Johnson',
    phone: '7890123456',
    email: '@bobgmail.com'
  },
  {
    id: 'emma',
    name: 'Emma Thompson',
    phone: '6543210987',
    email: '@emmagmail.com'
  }
]

        }
    },

}

</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Jost&display=swap');
</style>