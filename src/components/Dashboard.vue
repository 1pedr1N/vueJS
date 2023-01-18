<template>
   <div id="burguer-table">
<div> 
    <div id="burguer-table-heading">
        <div class="order-id">#:</div>
        <div class="order-name">Cliente:</div>
        <div class="order-pao">Pão:</div>
        <div class="order-carne">Carne:</div>
        <div class="order-opcionais">Opcionais:</div>
        <div class="order-status">Ações:</div>
    </div>
</div>
<div id="burguer-table-rows">
    <div class="burguer-table-row">
        <div class="order-number"></div>
        <div>Joao</div>
        <div>Integral</div>
        <div>Frango</div>
      <ul>
        <li>salame</li>
        <li>2x salame</li>
      </ul>
<div>
    <select name="status" class="status">
        <option value=""> Selecione</option>
    </select>
    <button class="delete-btn">Cancelar </button>
</div>
    </div>
    
</div>
   </div>
</template>


<script >
export default {
    name: "DashBoard",
}
</script>
<style scoped>
.status{
    margin-left: 120px;
}
#burguer-table{
    max-width: 1200px;
    margin : 0 auto;
}

#burguer-table-heading,#burguer-table-rows,.burguer-table-row{
display: flex;
flex-wrap: wrap;
}
#burguer-table-heading{
    font-weight: bold;
    padding:12px;
    border-bottom: 3px solid #3333;
}
#burguer-table-heading div,
.burguer-table-row div{
    width: 19%;
}
.burguer-table-row{
    width: 100%;
    padding:12px;
    border-bottom:1px solid #ccc
}
#burguer-table-heading .order-id, .burguer-table-row .order-number{
    width: 5%;
}
select{
    padding:12px 6px;
    
    margin-right: 12px;
}
.delete-btn{
    
    background-color: #222;
    color:#fcba03;
    font-weight: bold;
    border: 2px solid #222;
    padding:10px;
    font-size: 16px;
    margin:0 auto;
    cursor: pointer;
    transition: 0.5s;
margin-left: 120px;
}
.delete-btn:hover{
    background-color: #fcba03;
    color:#222;
}
</style>