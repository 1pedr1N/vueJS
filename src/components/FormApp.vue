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
        <div class="input-container">
            <label for="opcionais">Escolha sua opcionais:</label>
    <div class="checkbox-container">
        <input type="checkbox" name="opcionais" v-model='opcionais' value="salame">
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
<style scoped></style>
