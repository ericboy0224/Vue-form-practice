<template>
<user-data @add-data="addData"></user-data>
<active-user v-for="(item, index) in items" :key="index"
:name="item.name"
:age="item.age"
></active-user>

</template>

<script>
import ActiveUser from './components/ActiveUser.vue'
import UserData from './components/UserData.vue'
export default {
  components: { UserData, ActiveUser },
data() {
    return {
        items:[]
    }
},
methods: {
    addData(name, age){
        const goingToAdd = {
            id:new Date().toISOString(),
            name: name,
            age: age
        };
        this.items.push(goingToAdd);
    }
},
}
</script>

<style>
:root {
  --color-primary: #2eec96;
  --selection-color: #abffd9;
  --unitless-max-font-size: 18;
}

body {
  padding: 2rem 1rem;
  background-color: #2eec96;
}

form,ul {
  max-width: 30rem;
  margin: 0 auto;
  padding: 1.5rem 2rem;
  background-color: white;
  border-radius: 8px;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.15);
}
ul{
  margin-top: 20px;
}

form h1 {
  margin-bottom: 1.5rem;
  padding-bottom: 1rem;
  border-bottom: 1px solid var(--gray-lighter);
  font-size: var(--font-size-3);
  text-align: center;
}

input {
  background-repeat: no-repeat;
  background-position: right 1rem center;
  background-size: 0.75rem;
  width: 100%;
  height: 30px;
  text-align: left;
  
 }

p{
    width: 70%;
    margin: auto;
}
input:placeholder-shown + label {
  opacity: 0;
  transform: translateY(1rem);
}

.has-dynamic-label {
  position: relative;
  padding-top: 1.5rem;
}

.has-dynamic-label label {
  position: absolute;
  top: 0;
  font-size: var(--font-size-small);
  opacity: 1;
  transform: translateY(0);
  transition: all 0.2s ease-out;
}



input:read-only {
  border-color: var(--gray-lighter) !important;
  color: var(--gray);
  cursor: not-allowed;
}

input:valid {
  border-color: var(--color-primary);
  background-image: url("data:image/svg+xml,%3Csvg width='45px' height='34px' viewBox='0 0 45 34' version='1.1' xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink'%3E%3Cg stroke='none' stroke-width='1' fill='none' fill-rule='evenodd'%3E%3Cg transform='translate%28-56.000000, -59.000000%29' fill='%232EEC96'%3E%3Cpolygon points='70.1468531 85.8671329 97.013986 59 100.58042 62.5664336 70.1468531 93 56 78.8531469 59.5664336 75.2867133'%3E%3C/polygon%3E%3C/g%3E%3C/g%3E%3C/svg%3E%0A");
}

input:invalid {
  border-color: var(--color-error);
  background-image: url("data:image/svg+xml,%3Csvg width='30px' height='30px' viewBox='0 0 30 30' version='1.1' xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink'%3E%3Cg stroke='none' stroke-width='1' fill='none' fill-rule='evenodd'%3E%3Cg transform='translate%28-128.000000, -59.000000%29' fill='%23F44336'%3E%3Cpolygon points='157.848404 61.9920213 145.980053 73.8603723 157.848404 85.7287234 154.856383 88.7207447 142.988032 76.8523936 131.119681 88.7207447 128.12766 85.7287234 139.996011 73.8603723 128.12766 61.9920213 131.119681 59 142.988032 70.8683511 154.856383 59'%3E%3C/polygon%3E%3C/g%3E%3C/g%3E%3C/svg%3E%0A");
}

input:invalid:focus {
  border-color: var(--color-error);
}
.contain-btn{
    display: block;
}
.btn {
      /* 文字颜色 */
      color: #2eec96; 
      
      background: transparent; 
      
      border: 2px solid #0099CC;
      
      border-radius: 6px; 
      
      border: none;
      color: white;
      padding: 16px 32px;
      text-align: center;
      display: inline-block;
      font-size: 16px;
      margin: 20px 10px 10px 10px ;
      -webkit-transition-duration: 0.4s; /* Safari */
      transition-duration: 0.4s;
      cursor: pointer;
      text-decoration: none;
      text-transform: uppercase;
}
.btn{
      background-color: white; 
      color: black; 
      border: 2px solid transparent;
      width: 100%;
}
/* 悬停样式 */
.btn:hover {
      background-color: #2eec96;
      color: white;
}
</style>
