<template>
    <section>
        <header>
            <h1>My Friends</h1>
        </header>

        <new-friend @add-contact="addContact"></new-friend>
        <ul>
            <friend-contact
            v-for="friend in friends"
            :key="friend.id"
            :id="friend.id"
            :name='friend.name'
            :phone-number='friend.phone'
            :email-address='friend.email'
            @delete="deleteContact"
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

    methods: {
      addContact(name, phone, email, id) {
        const newFriendContact = {
          id: id,
          name: name,
          phone: phone,
          email: email
        }
        
        this.friends.push(newFriendContact);
      },

      deleteContact(friendId){
        this.friends = this.friends.filter((friend) => friend.id !== friendId);
      }
    }

}

</script>

<style>
  
@import url('https://fonts.googleapis.com/css2?family=Jost&display=swap');

* {
  box-sizing: border-box;
}

html {
  font-family: 'Jost', sans-serif;
}

body {
  margin: 0;
}

header {
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
  margin: 3rem auto;
  border-radius: 10px;
  padding: 1rem;
  background-color: #58004d;
  color: white;
  text-align: center;
  width: 90%;
  max-width: 40rem;
}

#app ul {
  margin: 0;
  padding: 0;
  list-style: none;
}

#app li,
#app form
{
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
  margin: 1rem auto;
  border-radius: 10px;
  padding: 1rem;
  text-align: center;
  width: 90%;
  max-width: 40rem;
}

#app h2 {
  font-size: 2rem;
  border-bottom: 4px solid #ccc;
  color: #58004d;
  margin: 0 0 1rem 0;
}

#app button {
font: inherit;
cursor: pointer;
border: 1px solid #ff0077;
background-color: #ff0077;
color: white;
padding: 0.05rem 1rem;
box-shadow: 1px 1px 2px rgba(0, 0, 0, 0.26);
}

#app button:hover,
#app button:active {
background-color: #ec3169;
border-color: #ec3169;
box-shadow: 1px 1px 4px rgba(0, 0, 0, 0.26);
}

#app input {
    font: inherit;
    padding: 0.15rem;
}

#app label {
    font-weight: bold;
    margin-right: 1rem;
    width: 7rem;
    display: inline-block;
}

#app form div {
    margin: 1rem ;
}
</style>