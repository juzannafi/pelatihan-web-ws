<template>
    <div class="card" style="width: 18rem;">
       <div class="card-body">
          <h5 class="card-title">{{ mataKuliah }}</h5>
          <p class="card-text"> {{ namaTugas }} </p>
          <p class="card-text"> {{ deadline }} </p>
       </div>
      </div>
</template>

<script>
export default {
    props: {
        mataKuliah: String,
        namaTugas: String,
        deadline: String,
    }
}
</script>

<style>

</style>