<template>
  <div class="container">
      <form @submit.prevent="submitData">
          <h1>Component Practice</h1>
          <p class="has-dynamic-label">
              <input type="text" v-model="enterName" placeholder="Enter name" required/>
          <label for="dynamic-label-input" >Enter name</label>
          </p>
          <p class="has-dynamic-label">
              <input v-model="enterAge" placeholder="Enter Age" required/>
              <label for="dynamic-label-input">Enter Age</label>
              </p>
      
          <div class="contain-btn "><button class="btn">ADD</button></div>
      </form>
  </div>
</template>

<script>
export default {
    data() {
        return {
            enterName:'',
            enterAge:''
        }
    },
    emits:['add-data'],
    methods: {
        submitData(){
            this.$emit('add-data', this.enterName, this.enterAge);
            
        }
    },
}
</script>
