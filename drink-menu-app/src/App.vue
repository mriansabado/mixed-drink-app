<script setup>

</script>

<template>
  <div class="main-container">

    <div class="img-container">
     <div class="box img-item"></div>
    </div>

    <div class="search-container box">
      <div class="box query1">
        <h3>Search for a Drink by name</h3>
      </div>
      <div class="box query2">
       <h3>More Information on Alcohol</h3>
      </div>
      <div class="box query3">
        Generate a Random Drink
      </div>
    </div>



  </div>

  
</template>

<style scoped>
 .img-container {
  display: flex;
  justify-content: center;
  height: 40vh;
 }

 .img-item {
  width: 60vw;
 }

 .search-container {
  margin-top: 20px;
  display: grid;
  justify-content: center;
  


 }
</style>
