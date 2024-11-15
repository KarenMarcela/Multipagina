<script setup> //permite una sintaxis mucho mas sencilla, mas corta
    import {ref} from 'vue'

    let qty =ref(0) //Estoy volviendo reactiva a esta variable (Pasa a ser un objeto)

    function add() {
        qty.value++
        console.log(qty)
    }
    function deleteM() {
        qty.value--
        console.log(qty)
        if(qty.value < 0){
            qty.value = 0;
            alert("No es posible realizar la resta, ya se encuentra en cero")
        }

    }
</script>
<!-- TODO LO QUE SEA HTML DENTRO DE VUE SE DEBE PONER EN UNA ETIQUETA ESENCIAL TEMPLATE -->
<template>
    <div class="max-w-80 mx-auto bg-purple-300 p-6">
        <!-- INTERPOLACION DE VALORES -->
         <!-- V-SHOW es para mostrar o quitar cosas -->
        <div v-if="qty > 0 " 
            class="bg-red-500 text-white rounded-full size-8 flex justify-center items-center font-bold"
            :class="{'bg-orange-500':qty > 3}"
        >
            {{  qty }}
        </div>
        <div v-else>
            Nadie te visita :(
        </div>
        <div
            @click="add"  ,
            class="bg-blue-400 text-white rounded size-6 flex justify-center items-center"
        >
            +
        </div>
        <div
            @click="deleteM"  ,
            class="bg-red-400 text-white rounded size-6 flex justify-center items-center"
        >
            -
        </div>

    </div>
</template>