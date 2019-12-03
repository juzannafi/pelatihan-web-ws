<template>
  <div id="app" class="container">
    <div class="row justify-content-around">
      <!-- <div v-for="(item, index) in tugas" :key="index" class="card" style="width: 18rem;">
       <div class="card-body">
          <h5 class="card-title">{{ item.mataKuliah }}</h5>
          <p class="card-text"> {{item.namaTugas}} </p>
          <p class="card-text"> {{item.deadline}} </p>
       </div>
      </div> -->

      <item-card v-for="(item, index) in tugas" :key="index" v-bind:mataKuliah="item.mataKuliah" :namaTugas="item.namaTugas" :deadline="item.deadline">     
      </item-card>

      <!-- div dihapus karena menggunakan for -->
      <!-- <div class="card" style="width: 18rem;">
       <div class="card-body">
          <h5 class="card-title">Basdat</h5>
          <p class="card-text">Laporan Praktikum</p>
          <p class="card-text">20 November</p>
          <a href="#" class="btn btn-primary">Go somewhere</a>
       </div>
      </div>

      <div class="card" style="width: 18rem;">
       <div class="card-body">
          <h5 class="card-title">Pemodelan dan Simulasi</h5>
          <p class="card-text">Presentasi </p>
          <a href="#" class="btn btn-primary">Go somewhere</a>
       </div>
      </div> -->
    </div>
    <!-- Button trigger modal -->
<button type="button" class="btn btn-primary" data-toggle="modal" data-target="#exampleModalCenter">
  Tambah
</button>

<!-- Modal -->
<div class="modal fade" id="exampleModalCenter" tabindex="-1" role="dialog" aria-labelledby="exampleModalCenterTitle" aria-hidden="true">
  <div class="modal-dialog modal-dialog-centered" role="document">
    <div class="modal-content">
      <div class="modal-header">
        <h5 class="modal-title" id="exampleModalCenterTitle">Modal title</h5>
        <button type="button" class="close" data-dismiss="modal" aria-label="Close">
          <span aria-hidden="true">&times;</span>
        </button>
      </div>
      <div class="modal-body">
        <div class="row">
              <input class="col-12 form-control" type="text" placeholder="Mata Kuliah" v-model="mata_Kuliah">
              <input class="col-12 form-control" type="text" placeholder="Nama Tugas" v-model="nama_Tugas">
              <input class="col-12 form-control" type="text" placeholder="Deadline" v-model="dead_line">

        </div>
      </div>
      <div class="modal-footer">
        <button type="button" class="btn btn-secondary" data-dismiss="modal">Close</button>
        <button @click="simpanData" type="button" data-dismiss="modal" class="btn btn-primary">Save changes</button>
      </div>
    </div>
  </div>
</div>
  </div>
</template>

<script>
import itemCard from './components/itemCard'

export default {
  name: 'app',
  components: {
    itemCard
  },
  data(){
    return{
      mata_Kuliah: '',
      nama_Tugas: '',
      dead_line: '',
      tugas: [
        // {
        //   mataKuliah: 'ISIS', 
        //   namaTugas: 'Fourier Transform',
        //   deadline: '20 November 2019'
        // },
        // {
        //   mataKuliah: 'Basis Data', 
        //   namaTugas: 'Laporan Praktikum',
        //   deadline: '20 November 2019'
        // },
        // {
        //   mataKuliah: 'Pemodelan dan Simulasi', 
        //   namaTugas: 'Presentasi SPBL',
        //   deadline: '20 November 2019'
        // },
        // {
        //   mataKuliah: 'Jaringan Komputer', 
        //   namaTugas: 'Presentasi',
        //   deadline: '21 November 2019'
        // },
        // {
        //   mataKuliah: 'Perencanaan Rekayasa', 
        //   namaTugas: 'Presentasi SPBL',
        //   deadline: '21 November 2019'
        // },
        // {
        //   mataKuliah: 'Keamanan dan Integritas Data', 
        //   namaTugas: 'Wawancara',
        //   deadline: '21 November 2019'
        // }
      ]
    }
  },
  methods: {
    simpanData(){
      let data = {
          mataKuliah: this.mata_Kuliah,
          namaTugas: this.nama_Tugas,
          deadline: this.dead_line
      }
      this.tugas.push(data)
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.card{
  margin: 16px
}

.input{
  margin: 10px
}

</style>
