<template>
  <!-- <div class="container"> -->
    <div class="row " style="height: 599px;"> 
      <div class="col-8">
          <div class=" row  justify-content-center">
            <img  height="20" width="20" src="https://www.google.com/url?sa=i&url=https%3A%2F%2Fes.pngtree.com%2Ffreepng%2Fstar-cartoon-cartoon-stars-icon_3816664.html&psig=AOvVaw3Tqiig_S1_bCMjlhptnWjG&ust=1583551973037000&source=images&cd=vfe&ved=0CAIQjRxqFwoTCMCo8_z0hOgCFQAAAAAdAAAAABAF" alt="">
          </div>
          <div class=" row mt-2 justify-content-center">
            <p>
              Enter your numbre to ear
            </p>
            <p>
              rewards
            </p>
          </div>
          <div class="row my-4 justify-content-center ">
            <p style="font-size: 10px;">es simplemente el texto de relleno de las imprentas </p>
          </div>
          <div class="row justify-content-center">
              <el-button type="danger" plain  @click="openModal">View Details</el-button>
          </div>
      </div>
      <div class="col-4 text-white" style="background-color:#390a65;">
          <div class="row justify-content-center mb-4">
              <p class="px-2 mx-2">Digite su numero</p>
          </div>
          <div class="row mb-4">
            <el-input placeholder="Please input" v-model="input"/>
          </div>
          <div class="row mb-1">
            <div class="col-4 px-0">
              <el-button class="w-100" @click="numero(1)">1</el-button>
            </div>
            <div class="col-4 px-0">
              <el-button class="w-100" @click="numero(2)">2</el-button>
            </div>
            <div class="col-4 px-0">
              <el-button class="w-100" @click="numero(3)">3</el-button>
            </div>
          </div>
          <div class="row mb-1">
            <div class="col-4 px-0">
              <el-button class="w-100" @click="numero(4)">4</el-button>
            </div>
            <div class="col-4 px-0">
              <el-button class="w-100" @click="numero(5)">5</el-button>
            </div>
            <div class="col-4 px-0">
              <el-button class="w-100" @click="numero(6)">6</el-button>
            </div>
          </div>
          <div class="row mb-1">
            <div class="col-4 px-0">
              <el-button class="w-100" @click="numero(7)">7</el-button>
            </div>
            <div class="col-4 px-0">
              <el-button class="w-100" @click="numero(8)">8</el-button>
            </div>
            <div class="col-4 px-0">
              <el-button class="w-100" @click="numero(9)">9</el-button>
            </div>
          </div>
          <div class="row mb-1">
            <div class="col-4 px-0">
              <el-button class="w-100" @click="limpiar">x</el-button>
            </div>
            <div class="col-4 px-0">
              <el-button class="w-100" @click="numero(0)">0</el-button>
            </div>
            <div class="col-4 px-0">
              <el-button class="w-100" @click="borrar">
                h
              </el-button>
            </div>
          </div>
          <div class="row my-4">
            <el-button class="w-100" @click="checkIn">
              check in
            </el-button>
          </div>
      </div>
      <!-- modal -->              
        <el-dialog
          title="Data"
          :visible.sync="centerDialogVisible"
          width="50%"
          center>
          <div class="col-12">
            <div class="row mb-2">
              <el-input v-model="name" placeholder="name" />
            </div>
            <div class="row">
              <el-input v-model="email" placeholder="email" />
            </div>
          </div>          
          <span slot="footer" class="dialog-footer">
            <el-button type="success" class="text-white" @click="registar">Validar</el-button>
          </span>
        </el-dialog>
    </div>
  <!-- </div> -->
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data(){
    return {
      input: '',
      centerDialogVisible: false,
      email:'',
      name:''
    }
  },
  methods:{
    numero(data){
      this.input = `${this.input}${data}`
    },
    limpiar(){
      this.input = ''
    },
    borrar(){
      this.input = this.input.substring(0, this.input.length-1)
    },
    openModal(){
      this.centerDialogVisible = true
    },
    registar(){
      if (this.name != '' && this.email != '') {
        this.centerDialogVisible = true
      } else {
        alert('ingrese nombre y email')
      }
    },
    checkIn(){
      if (this.imput=='') {
        alert('escriba el numero telefonico')
        return
      }
      alert('registrado con exito')
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
