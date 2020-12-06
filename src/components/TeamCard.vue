<template>
    <div class="card text-black bg-white">
        <div class="d-flex justify-content-center p-2">
            <span class="shadow p-3 bg-white rounded"><img class="img-fluid" v-bind:src='member.image' alt="Foto"></span>
        </div>

        <div class="card-body">
            <h3 class="card-title">{{ member.nombre }}</h3>
            <p class="card-text"><span><b>Codigo: </b></span>{{ member.codigo }}</p>
            <p class="card-text"><span><b>Rol: </b></span>{{ member.rol }}</p>
            <p class="card-text">{{ member.descripcion }}</p>
        </div>
    </div>
</template>

<script>
    export default {
        name: "TeamCard",
        props: {
            'member' : Object
        }
    }
</script>

<style scoped>

</style>
