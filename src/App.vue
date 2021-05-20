<template>
    <div id="app">
       <h2>Crea una nueva tarea</h2>
       <div class="form_container">
           <h3>Tarea</h3>
           <input v-model='input' type="text" placeholder="Ingresa nueva tarea">
           <button @click='addToList'>Crear</button>
       </div>
       <h2>Lista</h2>
       <ol>
           <li v-for='tarea in tareas'>
               {{tarea}}
           </li>
       </ol>
           <button v-if='tareas.length>0' @click='removeFromList'>Remover tarea</button>
    </div>
</template>

<script>
export default {
    name: "App",
    data() {
        return {
        input:'',
        tareas: []
        }
    },
    methods: {
        addToList(){
            this.input ==''? alert('Debes escribir una tarea para que sea ingresada !'):
            this.tareas.push(this.input);
            this.input=''
        },
        removeFromList(){
            this.tareas.length > 0? this.tareas.pop():
            false
        }
    }
}

</script>
<style scoped>
    
    #app{
        margin: 0;
        padding: 0;
        box-sizing: border-box;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center ;
        background-image: url('https://res.cloudinary.com/practicaldev/image/fetch/s--BuPz-p40--/c_imagga_scale,f_auto,fl_progressive,h_420,q_auto,w_1000/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/nphrgz8yfnjylrwfr0yl.png');
        height: 100vh;
        color: white;
    }
    .form_container{
        display: flex;
        flex-direction: row;
        align-items: center;
        justify-content: center;
        height: 30px;
    }
    input{
        margin: 0 3px
    }
   
</style>
