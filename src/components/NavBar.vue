<template>
  <nav class="main-nav">

    <router-link :to = "{ name: 'home'}">Projects</router-link>


    <router-link :to = "{ name: 'AddProject'}">Add a New Project</router-link>

  </nav>

</template>

<script>
export default {

}
</script>

<style>
  .main-nav{
    text-align: center;
    margin: 40px auto;
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: center;
    gap: 30px
  }

  .main-nav a{
    text-decoration: none;
    color: #999;
    font-size: 18px;
  }

  a.router-link-active {
    border-bottom: 2px solid #00ce89;
    padding-bottom: 4px;
  }
</style>