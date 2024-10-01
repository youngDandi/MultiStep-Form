<script>

export default{
    name: 'StepTwo',
  emits: ['next-step', 'previous-step'],
};
</script>

<template>
    <div class="formTwo">
        
        <a href="#" @click.prevent="$emit('previous-step')" id="previous">
            <span class="arrow-left">&#x2190;</span>
            Passo Anterior
        </a>
        <div class="input-groupTwo">
            <input type="text" required/>
            <label for="">Número de Telefone</label>    
        </div>
        <h2 class="interestFild">Área de Interesse</h2>
        <div class="checkbox-group">
            <div class="checkSpan">
                <input type="checkbox" id="desenvolvimento" name="interesse" value="desenvolvimento" class="check-input">
                <label for="desenvolvimento" class="checkbox">
                    <svg viewBox="0 0 22 16" fill="none" v-if="checked">
                        <!-- Aqui você pode adicionar o conteúdo SVG -->
                        <path d="M1 8l6 6L21 1" stroke="#01b681" stroke-width="2"/>
                    </svg>
                </label>
                <span>Desenvolvimento</span>
            </div>
            
            <div class="checkSpan">
                <input type="checkbox" id="design" name="interesse" value="design" class="check-input">
                <label for="design" class="checkbox">
                    <svg viewBox="0 0 22 16" fill="none" v-if="checked">
                        <!-- Aqui você pode adicionar o conteúdo SVG -->
                        <path d="M1 8l6 6L21 1" stroke="#01b681" stroke-width="2"/>
                    </svg>
                </label>    
                   <span>Design</span> 
            </div>
            
            <div class="checkSpan">
                <input type="checkbox" id="marketing" name="interesse" value="marketing" class="check-input">
                <label for="marketing" class="checkbox">
                    <svg viewBox="0 0 22 16" fill="none" v-if="checked">
                        <!-- Aqui você pode adicionar o conteúdo SVG -->
                        <path d="M1 8l6 6L21 1" stroke="#01b681" stroke-width="2"/>
                    </svg>
                    
                </label>
                <span>Marketing</span>
            </div>

            
        </div>
        <button id="btnTwo" @click="$emit('next-step')">Avançar</button>
        
    </div>

</template>

<style>
.formTwo{
    display: flex;
    flex-direction: column;
    gap: 1px;
    width: 100vh;
    height: 100vh;
    position: relative;
    align-items: center;
    margin-top: 10%;
    
}

#previous{
  display: flex;
  margin-right: 52%;
}

a{
    color: #a4a6a8;
}

.input-groupTwo {
    position: relative;
    margin: 10px 0;
    align-items: center;
    margin-top: 5%;
}


.input-groupTwo label{
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

.input-groupTwo input{
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

.input-groupTwo input:focus~label,
.input-groupTwo input:valid~label {
    top: 0;
    font-size: 12px;
    color: #01b681;
    
}

.input-groupTwo input:focus {
    border-color: #01b681;
}

.interestFild{
    border-bottom: 1px solid #a4a6a8;
    width: 420px;   
    text-align: left; /* Alinha o texto ao início */
    margin: 0; /* Remove o espaçamento padrão do h2 */
    padding: 0; /* Remove qualquer espaçamento interno que possa estar afastando o texto */
    margin-top: 3%;
}

#marketing{
    border-radius: 50%;
}

.checkbox-group {
  display: flex;
  flex-direction: column;
  gap: 10px;
  margin-top: 3%;
  margin-right: 44%;
   
}

.checkSpan{
    display: flex;
    flex-direction: row;
    gap: 10px;
    align-items: center;
    margin-top: 3%;
    
}

.check-input {
  display: none;
  
}

.checkbox {
  width: 15px;
  height: 15px;
  border: 2px solid #dee2e6;
  border-radius: 50%;
  display: flex;
  justify-content: center;
  align-items: center;
  cursor: pointer;
  padding: 1px;
  transition: 0.3s all;
  position: relative; /* Necessário para o efeito ripple */
  
}

.checkbox svg {
  width: 20px;
  height: 20px;
}

.check-input:checked + .checkbox {
  background: #01b681;
  border: 2px solid #01b681;
}

.check-input:checked + .checkbox svg path {
  stroke-dasharray: 500;
  stroke-dashoffset: 500;
  stroke: #a4a6a8;
  stroke-width: 3;
  animation: check 4s forwards;
}

.checkbox::before {
  content: "";
  background: #26bfbf66;
  position: absolute;
  border-radius: 50%;
  transform: scale(0);
  display: block;
  width: 60px;
  height: 60px;
  z-index: -1;
}

.check-input:checked + .checkbox::before {
  animation: ripple 0.3s;
}


@keyframes check {
  to {
    stroke-dashoffset: 0;
  }
}

@keyframes ripple {
  to {
    transform: scale(0.6);
  }
}

#btnTwo{
    background-color: #01b681;
    width: 230px;
    height: 60px;
    color: white;
    margin-top: 6%;
    border-color: #01b681;
}
</style>