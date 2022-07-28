<!-- <template>
    <h3 class="text-pink-300">This is about page</h3>
</template>
<script>
// This will also work in `<script setup>`
definePageMeta({
  layout: "custom",
   title: 'My Contact page'

});
</script> -->

<template>
    <div>
        <input v-model = "formData.firstName" type="text">
        <p>
            Name : {{formData.firstName}}
        </p>
    </div>
</template>


<script setup lang="ts">

const formData =reactive({
    firstName: ''
    // lastName: "Mali", 
    // email: "sona@gmail.com",
    // contact: 9028564356,

    
});
</script>