<template>
    <a><img :id="id" :src="imageURL" alt="id"></a> 
</template>

<script>
export default {
   props: ['imageURL', 'id']
}
</script>

<style scoped>
img {
    width: 50px;
    cursor: pointer;
    user-select: none;
}
</style>