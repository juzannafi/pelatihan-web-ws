<template>
    <div>
        <p v-for="(item, index) in pesan" :key="index"> {{item}} </p>
    </div>
</template>

<script>
export default {
    data(){
        return{
            pesan: ['Ohayou', 'Konnichiwa', 'Konbanwa']
        }
    }

}
</script>

<style>

</style>