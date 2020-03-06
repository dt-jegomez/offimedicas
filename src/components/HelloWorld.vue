<template>
  <!-- <div class="container"> -->
    <div class="row mx-0 " id="morado" style=""> 
      <div class="col-8">
          <div class=" row  justify-content-center">
            <img   src="https://pngimage.net/wp-content/uploads/2018/05/estrellas-ue-png-6-300x200.png" alt="">
          </div>
          <div class=" row mt-2 justify-content-center">
            <p  class="w-100 text-center" style="font-size: 30px;"> Enter your number to ear </p>
            <p class="w-100 text-center"> rewards </p>
          </div>
          <div class="row my-4 justify-content-center ">
            <p style="font-size: 10px;">es simplemente el texto de relleno de las imprentas </p>
          </div>
          <div class="row btn-hover-purple justify-content-center">
              <el-button plain  @click="openModal">View Details</el-button>
          </div>
      </div>
      <div class="col-4 btn-purple text-white" style="background-color:#390a65; border-bottom-left-radius: 10px; border-top-left-radius: 10px;">
          <div class="row justify-content-center my-4">
              <p class="px-2 mx-2" style="color:#a66bdd;">Digite su numero</p>
          </div>
          <div class="row mb-4 px-3">
            <input placeholder="Please input" v-model="input" class="form-control" style="color:#a66bdd; background-color: #a571e4;"/>
          </div>
          <div class="row mb-1 px-2">
            <div class="col-4 px-1 mb-1" >
              <el-button class="w-100" @click="numero(1)" style="font-size: 30px;">1</el-button>
            </div>
            <div class="col-4 px-1 mb-1" > 
              <el-button class="w-100" @click="numero(2)" style="font-size: 30px;">2</el-button>
            </div>
            <div class="col-4 px-1 mb-1" > 
              <el-button class="w-100" @click="numero(3)" style="font-size: 30px;">3</el-button>
            </div>
          </div>
          <div class="row mb-1 px-2">
            <div class="col-4 px-1 mb-1">
              <el-button class="w-100" @click="numero(4)" style="font-size: 30px;">4</el-button>
            </div>
            <div class="col-4 px-1 mb-1">
              <el-button class="w-100" @click="numero(5)" style="font-size: 30px;">5</el-button>
            </div>
            <div class="col-4 px-1 mb-1">
              <el-button class="w-100" @click="numero(6)" style="font-size: 30px;">6</el-button>
            </div>
          </div>
          <div class="row mb-1 px-2">
            <div class="col-4 px-1 mb-1">
              <el-button class="w-100" @click="numero(7)" style="font-size: 30px;">7</el-button>
            </div>
            <div class="col-4 px-1 mb-1">
              <el-button class="w-100" @click="numero(8)" style="font-size: 30px;">8</el-button>
            </div>
            <div class="col-4 px-1 mb-1">
              <el-button class="w-100" @click="numero(9)" style="font-size: 30px;">9</el-button>
            </div>
          </div>
          <div class="row mb-1 px-2">
            <div class="col-4 px-1 mb-1">
              <el-button class="w-100" @click="limpiar" style="font-size: 30px;">x</el-button>
            </div>
            <div class="col-4 px-1 mb-1">
              <el-button class="w-100" @click="numero(0)" style="font-size: 30px;">0</el-button>
            </div>
            <div class="col-4 px-1 mb-1">
              <el-button class="w-100" @click="borrar" style="font-size: 30px;">
                {{tecla}}
              </el-button>
            </div>
          </div>
          <div class="row my-4 px-2">
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
      name:'',
      tecla: "<"
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
<style lang="scss">
#morado{
    position: absolute;
    height: 100%;
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
    overflow: hidden;

}
.btn-purple{
  .el-button{
    background: #a66bdd;
  }
}
.btn-hover-purple{
  .el-button{
    background: white;
    color:#8400ff;
    border: 1px solid #a66bdd;
  }
  &:hover{
    .el-button{
      background: #a66bdd!important;
      color:#8400ff!important;
      border: 1px solid #a66bdd!important;
    }
  }
}
</style>
