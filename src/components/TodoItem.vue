<template>
  <li>  {{todo.title}}</li>
</template>

<script>
export default {
  props:{
      todo:{
          type:Object,
          required:true
      }
  }  
}
</script>