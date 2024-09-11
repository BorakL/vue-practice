<template>
    <div class="container-fluid bg-primary p-5">
      <h1 class="display-4 text-white">5. Two-Way Data Binding with an Object</h1>
      
      <p>First Name: {{ fullName.firstName }}</p>
      <p>Last Name: {{ fullName.lastName }}</p>
      
      <!-- Input to bind the full name -->
      <input 
        type="text" 
        class="form-control" 
        v-model="userFullName" 
        placeholder="Enter full name"
      >
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        fullName: {
          firstName: "",
          lastName: ""
        }
      };
    },
    computed: {
      userFullName: {
        get() {
          return `${this.fullName.firstName} ${this.fullName.lastName}`;
        },
        set(newValue) {
          // Split the new value into an array of names
            if(newValue.match(/\w+\s+\w+/)){
                console.log("newValue",newValue)
                const names = newValue.trim().split(" ");
                this.fullName.firstName = names[0];
                this.fullName.lastName = names.slice(1).join(" ")
            }else{
                this.fullName.firstName = newValue
                this.fullName.lastName = ""
            }
        }
      }
    }
  };
  </script>
  
  <style scoped>
  .bg-primary {
    padding: 2rem;
  }
  .display-4 {
    margin-bottom: 2rem;
  }
  </style>