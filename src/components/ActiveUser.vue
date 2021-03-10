<template>
  <ul>
      <li>
          <h2>
              Name: {{ name }}
          </h2>
          <h3>
              Age: {{ age }}
          </h3>
      </li>
  </ul>
</template>

<script>
export default {
    props:['id','name','age']

}
</script>
