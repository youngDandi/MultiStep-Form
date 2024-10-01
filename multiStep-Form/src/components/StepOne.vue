<script>

export default{
    name:'StepOne',
  emits: ['next-step'],
};
</script>

<template>
    <div class="form">
        
        <h2 id="PersonalInfo">Informação Pessoal</h2>
        <div class="input-group">
            <input type="text" required class="input"/>
            <label for="">Nome Completo</label>    
        </div>
        
        
        <div class="input-group">
            <input type="email" required class="input"/> 
            <label for=""> Endereco de Email </label>
        </div>
        
        <button id="btn" @click="$emit('next-step')">Avançar</button> 
    </div>
    

</template>

<style>


.form{
    display: flex;
    flex-direction: column;
    gap: 1px;
    width: 100vh;
    height: 115vh;
    position: relative;
    align-items: center;
    margin-top: 10%;
}

#PersonalInfo{
    display: flex;
    
    margin-right: 34%;
}

.input-group {
    position: relative;
    margin: 10px 0;
    margin-top: 2%;
}

.input-group label{
    position: absolute;
    top: 50%;
    left: 10px; /* Ajuste para dar espaço ao input */
    transform: translateY(-50%);
    font-size: 16px;
    padding: 0 5px;
    pointer-events: none;
    background: #fff; /* Cor de fundo para "cortar" a borda */
    transition: .5s;
}

.input-group input{
    border: 2px solid #dee2e6;
    border-radius: 5px;
    width: 420px;
    height: 50px;
    background: transparent;
    outline: none;
    font-size: 1.2em;
    line-height: 1.85;
    padding: 25px 15px 0;
}

.input-group input:focus~label,
.input-group input:valid~label {
    top: 0;
    font-size: 12px;
    color: #01b681;
    
}

.input-group input:focus {
    border-color: #01b681;
}



#btn{
    background-color: #01b681;
    width: 230px;
    height: 60px;
    color: white;
    margin-top: 3%;
    border-color: #01b681;
}

</style>