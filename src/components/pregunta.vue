<template>
    <img :src="img" alt="no se puede ver">
    <input v-model ="pregunta" type = text  placeholder="hazme una pregunra "/>
    <p>Recuerda que cuando finalices tu pregunta dar un ? </p>
    <h1>{{ pregunta }}</h1>
    <h2>{{ respuesta }}</h2>

</template>

<script>
export default {
    data(){
        return {
            pregunta:"Hola Mundo",
            respuesta:null,
            img:"https://yesno.wtf/assets/yes/12-e4f57c8f172c51fdd983c2837349f853.gif"
        }
    },
    watch:{
        pregunta(value, old_value){
            console.log(value)
            console.log(old_value)
            if(value.includes('?')){
                //programar la llamada al api para obtener el si/no
                //y la imagen 
                console.log('Aqui llamo al api')
               this.llamarAPI()
            }

        }
    },
    methods:{
        async llamarAPI(){
            const data = await fetch('https://yesno.wtf/api').then((resp) => resp.json());
            console.log(data)
            this.respuesta = data.answer;
            this.img = data.image;
            return data
        }
    }
}
</script>

<style>

</style>