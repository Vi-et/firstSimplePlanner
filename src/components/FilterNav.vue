<template>
  <nav class="filter-nav">
    <button @click="updateFilter('all')" :class="{ active : currentFilter === 'all' }">View All</button>
    <button @click="updateFilter('completed')" :class="{ active : currentFilter === 'completed' }">Completed</button>
    <button @click="updateFilter('ongoing')" :class="{ active : currentFilter === 'ongoing' }">Ongoing</button>

  </nav>
</template>

<script>
export default {
    methods:{
        updateFilter(by){
            this.$emit("filterChange", by)
        }
    },

    props : ['currentFilter']
}
</script>

<style>
    .filter-nav button{
        background: none;
        border: none;
        text-transform: uppercase;
        color: #BBBBBB;
        font-weight: bold;
        letter-spacing: 1px;
        margin-right: 10px;
        cursor: pointer;
    }

    .filter-nav button.active{
        color : #555
    }
</style>