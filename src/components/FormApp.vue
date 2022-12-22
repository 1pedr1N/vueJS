<!-- eslint-disable prettier/prettier -->
<template>
  <div class="main-container">
    <p>Componente de Mensagem</p>
    <form id="burguer-form">
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
          <option value="pao1">Pão Agridoce</option>
          <option value="pao2">Pão Baguete</option>
          <option value="pao3">Pão Queijo</option>
        </select>
      </div>
        <div class="input-container">
            <label for="carne">Escolha sua Carne:</label>
            <select id="carne" name="carne" v-model="pao">
                <option value="carne1">Ao Ponto</option>
                <option value="carne2">Mal Passada</option>
                <option value="carne3">Bem Passada</option>
            </select>
        </div>
        <div class="input-container" id="option">
            <label for="opcionais" id="option-ttl" >Escolha sua opcionais:</label>
 
      
        <div class="checkbox-container">
          <input type="checkbox" name="opcionais" v-model='opcionais' value="salame" class="checkbox-inpt">
          <span>salame</span>
        </div>
          <div class="checkbox-container">
            <input type="checkbox" name="opcionais" v-model='opcionais' value="salame" class="checkbox-inpt">
            <span>salame</span>
          </div>
            <div class="checkbox-container">
              <input type="checkbox" name="opcionais" v-model='opcionais' value="salame" class="checkbox-inpt">
              <span>salame</span>
            </div>
        </div>
        <div class="input-container">
            <input type="submit" class="sbm-btn" value="Criar meu hamburguer"/>
       
        </div>
    </form>
  </div>
</template>

<script>
export default {
  name: "FormApp",
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
  margin:0 auto;
}
.sbm-btn:hover {
  background-color: #fcba03;
  color: #222;
}
</style>
