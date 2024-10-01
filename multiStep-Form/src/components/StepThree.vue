<script>
export default{
    name: 'StepThree',
  emits: ['next-step', 'previous-step'],
};
</script>


<template>
    <div class="formThree">
        <p>Step 3</p>

        <a href="#" @click.prevent="$emit('previous-step')" id="previous">
            <span class="arrow-left">&#x2190;</span>
            Passo Anterior
        </a>
        
        <div class="input-groupThree">
            <textarea required></textarea>
            <label for="">Mensagem Opcional</label>
        </div>
        <div class="termsLabel">
            <input type="checkbox" />
            <label for="terms" > Eu aceito os
                <a href="#" class="terms"> Termos e Condições</a>
                e a
                <a href="#" class="terms">Política de Privacidade</a>
            </label>
        </div>
        <button id="btnThree">Avançar</button>
    </div>
</template>


<style>
.formThree{
    display: flex;
    flex-direction: column;
    gap: 1px;
    width: 100vh;
    height: 100vh;
    position: relative;
     align-items: center;
}
.input-groupThree {
  position: relative;
  margin: 10px 0;
  margin-top: 10%;
}

.input-groupThree label {
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

.input-groupThree textarea {
  border: 2px solid #dee2e6;
  border-radius: 5px;
  width: 420px;
  height: 100px; /* Ajuste de altura para o textarea */
  background: transparent;
  outline: none;
  font-size: 1.2em; /* Ajuste de tamanho da fonte para ser proporcional */
  line-height: 1.85;
  padding: 25px 15px 0; /* Adicionar padding para melhor aparência */
  resize: vertical; /* Permitir redimensionamento apenas na vertical */
}

.input-groupThree textarea:focus~label,
.input-groupThree textarea:valid~label {
  top: 0;
  font-size: 12px;
  color: #01b681;
}

.input-groupThree textarea:focus {
  border-color: #01b681;
}

.terms{
    color: #01b681;
}

.termsLabel{
  margin-top: 3%;
}

#btnThree{
    background-color: #01b681;
    width: 230px;
    height: 60px;
    color: white;
    margin-top: 3%;
    border-color: #01b681;
}
</style>