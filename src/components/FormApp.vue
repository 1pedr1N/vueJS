<!-- eslint-disable prettier/prettier -->
<!-- eslint-disable prettier/prettier -->
<!-- eslint-disable prettier/prettier -->
<template>
  <div class="main-container">
<MessageApp :msg="msg" v-show="msg" />
    <form id="burguer-form" @submit="createBurguer">
      <div class="input-container">
        <label for="name">Nome do Cliente</label>
        <input
          type="text"
          id="name"
          name="name"
          v-model="nome"
          placeholder="Digite seu nome"
        />
      </div>
      <div class="input-container">
        <label for="pao">Escolha seu Pão:</label>
        <select id="pao" name="pao" v-model="pao">
          <option :value="pao.tipo" v-for="pao in paes" :key="pao.id" >{{ pao.tipo }} </option>
   
        </select>
      </div>
        <div class="input-container">
            <label for="carne">Escolha sua Carne:</label>
            <select id="carne" name="carne" v-model="carne">
              <option :value="carne.tipo" v-for="carne in carnes" :key="carne.id">{{ carne.tipo }} </option>
            </select>
        </div>
        <div class="input-container" id="option">
            <label for="opcionais" id="option-ttl" >Escolha sua opcionais:</label>
 
      
        <div class="checkbox-container" v-for="opcional in opcionaisdata" :key="opcional.id" >
          <input type="checkbox" name="opcionais" v-model='opcionais' :value="opcional.tipo" class="checkbox-inpt">
          <span>{{ opcional.tipo }} </span>
        </div>
        </div>
        <div class="input-container">
            <input type="submit" class="sbm-btn" value="Criar meu hamburguer"/>
       
        </div>
    </form>
  </div>
</template>

<script>
import MessageApp from "./Message.vue";
export default {
  name: "FormApp",
  data() {
    return {
      paes: null,
      carnes: null,
      opcionaisdata: [],
      nome: null,
      pao: null,
      carne: null,
      opcionais: [],

      msg: null,
    };
  },
  methods: {
    async getIngredients() {
      const req = await fetch("http://localhost:3001/ingredientes");
      const data = await req.json();
      this.paes = data.paes;
      this.carnes = data.carnes;
      this.opcionaisdata = data.opcionais;
    },
    async createBurguer(e) {
      e.preventDefault();
      const data = {
        nome: this.nome,
        pao: this.pao,
        carne: this.carne,
        opcionais: Array.from(this.opcionais),
        status: "Solicitado",
        msg: this.msg,
      };
const dataJson = JSON.stringify(data);

const req = await fetch("http://localhost:3001/burgers", {
  method: "POST",
  headers: {
    "Content-Type": "application/json",
  },
  body: dataJson,
});
const res = await req.json();
console.log(res); 
this.msg = 'pedido foi'
this.nome = '';
this.pao = '';
this.carne = '';
this.opcionais = [];
this.msg = 'Pedido Realizado Com Sucesos';
setTimeout(() => this.msg = '', 3000)
 
    },
  },
  mounted() {
    this.getIngredients();
  },
  components: {
    MessageApp,
  },
};
</script>
<style scoped>
#burguer-form {
  max-width: 400px;
  margin: 0 auto;
}
.input-container {
  display: flex;
  flex-direction: column;
  margin-bottom: 20px;
}
label {
  margin-bottom: 15px;
  font-weight: bold;
  color: #222;
  padding: 5px 10px;
  border-left: 4px solid #fcba03;
}
input,
select {
  padding: 5px 10px;
  width: 300px;
}
#option {
  flex-direction: row;
  flex-wrap: wrap;
}
#option-ttl {
  width: 100%;
}
.checkbox-container {
  display: flex;
  flex-direction: row;
  align-items: center;
  width: 50%;
  margin-bottom: 20px;
}
.checkbox-container span,
.checkbox-container input {
  width: auto;
}
.checkbox-container span {
  margin-left: 6px;
  font-weight: bold;
}
.sbm-btn {
  background-color: #222;
  color: #fcba03;
  border: none;
  padding: 10px 20px;
  font-weight: bold;
  cursor: pointer;
  transition: all 0.3s ease;
  margin: 0 auto;
}
.sbm-btn:hover {
  background-color: #fcba03;
  color: #222;
}
</style>
