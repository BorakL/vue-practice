
<template>
    <div>
      <img :src="imageUrl" alt="Slika" width="200"/>
    </div>
    <button @click="changeImage">Promeni sliku</button>
  </template>

<script>
var imageUrl1 = "https://cdn.muscleandstrength.com/sites/default/files/leg-training-for-women.jpg";
var imageUrl2 = "https://n1info.rs/wp-content/uploads/2022/05/18/1652872279-bg-kapetan-sot-180522-zta-wmt.12_34_51_04.Still001-550x360.jpg"
export default {
    name: 'Execise1',
    data() {
        return {
              imageUrl: imageUrl1
        }
    },
    methods: {
      changeImage(){
        this.imageUrl = this.imageUrl===imageUrl1 ? imageUrl2 : imageUrl1
      }
    }
}
</script>


<style scoped>
p {
  color: blue;
}
</style>