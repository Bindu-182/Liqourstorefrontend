<template>
    <div class="liquor-store">
      <h2>Charger's Liquor Store</h2>
      <div v-for="liquor in liquors" :key="liquor._id" class="liquor-container" @click="showDetails(liquor)">
        <div class="image-container">
          <img :src="liquor.image" alt="Liquor Image" class="liquor-image" />
        </div>
        <div class="info-container">
          <h3>{{ liquor.name }}</h3>
          <p><strong>Type:</strong> {{ liquor.type }}</p>
          <p><strong>Description:</strong> {{ liquor.description }}</p>
          <p><strong>Brand:</strong> {{ liquor.brand }}</p>
          <p><strong>Price:</strong> ${{ liquor.price }}</p>
          <p><strong>Alcohol Percentage:</strong> {{ liquor.alcoholContent }}%</p>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    props: ['liquors'],
    methods: {
      showDetails(liquor) {
        console.log('Clicked on liquor:', liquor);
      }
    }
  };
  </script>
  
  <style scoped>
  .liquor-store {
  width: 100%;
  height: 100%;
  max-width: 800px;
  padding: 20px;
  margin: 0 auto; 
}
  
  .liquor-container {
    display: flex;
    border: 1px solid #ddd;
    margin-bottom: 20px;
    background-color: #c49c24;
    cursor: pointer;
    transition: transform 0.2s ease-in-out;
    border-radius: 8px;
    overflow: hidden;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  }
  
  .liquor-container:hover {
    transform: scale(1.02);
  }
  
  .image-container {
  flex: 0 0 auto;
  width: 150px; 
  height: 150px; 
  border-radius: 8px 0 0 8px;
  overflow: hidden;
}

.liquor-image {
  width: 100%;
  height: 100%;
  object-fit: fill;
  object-position: center; 
  border-radius: 8px 0 0 8px;
}
  
  .info-container {
    flex-grow: 1;
    padding: 20px;
  }
  
  
  h2, h3, p {
    color: #41261a;
    margin: 0px;
  }
  
  h3 {
    margin-bottom: 10px;
  }
  h2{
    color:#f89429;
    margin-bottom: 25px;
  }
  </style>
  