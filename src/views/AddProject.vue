<template>
  <form @submit.prevent="handleSubmit">
    <label for="">Title:</label>
    <input type="text" v-model="title" required>
    <label for="">Details:</label>
    <textarea v-model="details" required></textarea>
    <button>Add Project</button>
  </form>
</template>

<script>
export default {
    data(){
        return {
            title: "",
            details: ""
        }
    },
    methods: {
        handleSubmit() {
            let project = {
                title : this.title,
                details : this.details,
                complete: false
            }

            fetch("http://localhost:3000/projects", {
                method: 'POST',
                headers: {'Content-Type' : 'application/json'},
                body: JSON.stringify(project)
            }).then(() => this.$router.push("/"))
        }
    }
}
</script>

<style>
    form{
        background: white;
        border-radius: 10px;
        display: flex;
        flex-direction: column;
        padding: 20px 20px;
    }

    form label{
        text-transform: uppercase;
        font-weight: 600;
        letter-spacing: 1px;
        color: #bbb;
       

    }

    form input{
        border:none;
        border-bottom: #bbb solid 1px;
        margin: 10px 0 30px 0;
        padding: 10px

    }

    form button{
        margin:20px auto 0;
        display: block;
        background: #00ce89;
        border: none;
        text-align: center;
        padding: 10px;
        border-radius: 5px;
        color: white;
        cursor: pointer;
    }

    form textarea{
        margin-top: 10px;
        height: 200px;
        border: #bbb solid 1px;
        resize: none;
    }
</style>