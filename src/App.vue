<template>
 <div v-show="!isEditMode" id="display-view">
            <h1>User profile</h1>
            <img :src="image">
            
            <span>Name: </span><b id="name">{{ name }}</b>
            <hr />

            <span>Email: </span><b id="email">{{ email }}</b>
            <hr />

            <span>Interests: </span><b id="interests">{{ interests }}</b>
            <hr />

            <button @click="handleEditProfile()">Edit Profile</button>
        </div>
        <div v-show="isEditMode" id="edit-view">
            <h1>User profile</h1>
            <img :src="image">
            
            <span>Name: </span>
            <input type="text" id="input-name" v-model="name"/>
            <hr />

            <span>Email: </span>
            <input type="text" id="input-email" v-model="email" />
            <hr />

            <span>Interests: </span>
            <input type="text" id="input-interests"  v-model="interests" />
            <hr />

            <button @click="handleUpdateProfile()">Update Profile</button>
        </div>
</template>

<script>
import image from "./profile.jpeg"
export default  {
    name:"App",
    data (){
        return{
            image : image,
            name: "Anna Smith",
            email:"anna.smith@example.com",
            interests: "coding",
            isEditMode : "false "


        }
    },
    methods: {
        handleEditProfile() {
   this.isEditMode =true
},
handleUpdateProfile() {
    this.isEditMode =false
    
}

    }
}
</script>

<style>
img {
    width: 320px;
    height: 270px;
    display: block;
    margin-bottom: 40px;
}
div {
    margin: 40px auto;
    width: 80%;
}

hr {
    width: 400px;
    margin: 25px 0;
}

button {
    width: 160px;
    font-size: 15px;
    height: 45px;
    border-radius: 5px;
}

button:hover {
    cursor: pointer;
}

input {
    width: 200px;
    font-size: 15px;
    padding: 10px;
}


</style>