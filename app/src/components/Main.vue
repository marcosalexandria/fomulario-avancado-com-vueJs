<template>
    <div>
        <div v-for="pessoa in pessoa" :key="pessoa">
            <p>Nome: {{pessoa.nome}}</p>
            <p>Idade: {{pessoa.idade}}</p>
        </div>

        <form>
            <div>
                <input type="text" name="nome" id="nome" v-model="novaPessoa.nome">
            </div>
            <div>
                <input type="number" name="idade" id="idade" v-model="novaPessoa.idade">
            </div>
            <div>
                <button @click="add">Enviar</button>
            </div>

        </form>
    </div>
</template>

<script>

export default {
    name:'Main',

    data(){
        return{
           pessoa: [
               {
                   "nome":"Marcos",
                   "idade": 24
               },
               {
                   "nome":"Heloísa",
                   "idade": 6
               }
           ],
           novaPessoa:{}
           
        }
    },
    methods:{
        add(e){
            e.preventDefault();
            this.pessoa.push(this.novaPessoa);
        }
    }
}
</script>
