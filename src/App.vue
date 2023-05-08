<script setup>
import { ref, computed } from 'vue'

const nome = ref('')
const data = ref('')
const email = ref ('')
const senha = ref ('')
const confirma = ref ('')
const estado = ref('')
const endereco = ref('')
const cidade = ref('')
const hobby = ref('')
const linguagem = ref ('')
const biografia = ref('')
const mostrar = ref (false)

function confirme(){
  if(senha.value === confirma.value){
    return true
  } else{
    return false
  }
}
const mensagem = computed (() => {
  if(senha.value != confirma.value){
    return 'As senhas estão diferentes'
  }
  else{
    return ''
  }
})
  

</script>

<template>
  <form @submit.prevent="mostrar = confirme()">
    
   
    <label for="text">Nome: </label>
    <input type="text" v-on:keypress="ok= false" v-model="nome" required placeholder="digite seu nome" /> <br>
    
    <br>
    <label for="date">Data de nascimento: </label>
    <input type="date" v-on:keypress="ok= false" v-model="data" required placeholder="data de nascimento" /> <br>
    
<br>
   <label for="text">Endereço: </label>
    <input type="text" v-on:keypress="ok=false" v-model="endereco" required placeholder="Digite seu endereço" />
    
  
<br>
    <label for="text">Cidade: </label>
    <input type="text" v-on:keypress="ok=false" v-model="cidade" required placeholder="Digite sua cidade" />
    
<br>

    <label for="email">Email: </label>
    <input type="email" v-on:keypress="ok= false" v-model="email" required placeholder="digite seu email"/> <br>
   
<br>
<label for="text">Hobby: </label>
    <input type="text" v-on:keypress="ok= false" v-model="hobby" required placeholder="digite seu hobby"/> <br>
   
    <br>
    
    <label for="text">Linguagem de programação: </label>
    <input type="text" v-on:keypress="ok=false" v-model="linguagem" required placeholder="Digite sua linguagem" />
    
    <br>
    
    <label for="text">Biografia: </label>
    <textarea v-model="text" required placeholder="Digite sua biografia"/>
    
    <br>




   
  <label for="Estados">Estado: </label>
  <select v-on:keypress="ok =false" v-model="estado">
    
    <option value="AC">Acre</option>
    <option value="AL">Alagoas</option>
    <option value="AP">Amapa</option>
    <option value="AM">Amazonas</option>
    <option value="BA">Bahia</option>
    <option value="CE">Ceara</option>
    <option value="DF">Distrito Federal</option>
    <option value="ES">Espirito Santo</option>
    <option value="GO">Goias</option>
    <option value="MA">Maranhão</option>
    <option value="MT">Mato Grosso</option>
    <option value="MS">Mato Grosso do Sul</option>
    <option value="MG">Minas Gerais</option>
    <option value="PA">Pará</option>
    <option value="PB">Paraiba</option>
    <option value="PR">Paraná</option>
    <option value="PE">Pernambuco</option>
    <option value="PI">Piaui</option>
    <option value="RJ">Rio de Janeiro</option>
    <option value="RN">Rio Grande do Norte</option>
    <option value="RS">Rio Grande do Sul</option>
    <option value="RO">Rondônia</option>
    <option value="RR">Roraima</option>
    <option value="SC">Santa Catarina</option>
    <option value="SP">São Paulo</option>
    <option value="SE">Sergipe</option>
    <option value="TO">Tocantins</option>
  </select> 
  
  <br>

  <label for="password">senha: </label>
    <input type="password" v-on:keypress="ok= false" v-model="senha" required placeholder="digite sua senha"/><br>
  
    <br>
    <label for="password">confirmação de senha: </label>
    <input type="password" v-on:keypress="ok= false" v-model="confirma" required placeholder="digite novamente"/><br>
    
    <br>
    
    <button @click="mostrar = !mostrar"> confirmar</button>
    <p>{{ mensagem }}</p>
  </form>

    
<div v-if="mostrar" class="desaparece">
<p>O nome digitado é: {{ nome }}</p>
<br>
<p>O endereço é: {{ endereco}}</p>
<br>
<p>A cidade digitada é: {{ cidade}}</p>
<br>
<p>O email digitado é: {{ email}}</p>
<br>
<p>O hobby digitado é: {{ hobby }}</p>
<br>
<p>A linguagem de programação é: {{ linguagem}}</p>
<br>
<p>A biografia digitada é: {{ biografia}}</p>
<br>
<p>O estado escolhido é: {{estado}}</p>
<br>
<p>A senha digitada é: {{ senha }}</p>
<br>
<p>A confirmação digitada é:{{ confirma}}</p>
<br>
</div>

</template>
<style scoped>
* {
  padding: 0;
  margin: 0;
  
}
form {
  width: 30%;
  margin: 5em auto;
  padding: 3em;
  border : 2px solid rgb(0, 0, 0);
  border-radius: 10px;
  font-family: Georgia, 'Times New Roman', Times, serif;
  font-size: 16px;
  background-color:rgb(50, 108, 156);
  color: white;
}
input {
  width: 100%;
  padding: .8em;
}

select {
  width: 100%;
}

button {
  width: 100%;
  padding: .8em;
  color: rgb(0, 0, 0);
  text-transform: uppercase;
}
textarea{
 width: 100%;
 height: 50px;
}

.desaparece{
  width: 30%;
  margin: 5em auto;
  padding: 3em;
  border : 2px solid black;
  font-family: Georgia, 'Times New Roman', Times, serif;
  font-size: 16px;
  background-color:rgb(50, 108, 156);
  color: white;
  border-radius: 10px;

}

</style>