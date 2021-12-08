<template>
    <div id="app">
        <h1>Problema de Monty Hall</h1>
        <!--<Door number="1" :hasGift="false" /> : para passar o segundo parametro falso como boolean, sem os : passa como string -->
        <div class="form">
            <div v-if="!gameStarted">
                <label for="portsAmount">Quantas portas? </label>
                <input type="text" id="portsAmount" size="3"
                    v-model.number="portsAmount">
            </div>
            <div v-if="!gameStarted">
                <label for="selectedPort">Qual porta é premiada? </label>
                <input type="text" id="selectedPort" size="3"
                    v-model.number="selectedPort"> <!--two-way binding -->
            </div>
            <button v-if="!gameStarted" @click="gameStarted = true">Iniciar</button>
            <button v-if="gameStarted" @click="gameStarted = false">Reiniciar</button>
        </div>
        <div class="doors" v-if="gameStarted">
            <div v-for="i in portsAmount" :key="i">
                <Door :hasGift="i === selectedPort" :number="i" />
            </div>
        </div>
    </div>
</template>

<script>
import Door from "./components/Door";

export default {
    name: "App",
    components: {
        Door
    },
    data: function() {
        return{
            gameStarted: false,
            portsAmount: 3,
            selectedDoor: null
        }
    }

}
</script>

<style>
* {
    box-sizing: border-box;
    font-family: "Montserrat", sans-serif;
}

body {
    color: #fff;
    background: linear-gradient(to right, rgb(21, 153, 87), rgb(21, 87, 153));
}

#app {
    display: flex;
    flex-direction: column;
    align-items: center;
}

#app h1 {
    border: 1px solid #000;
    background-color: #0004;
    padding: 20px;
    margin-bottom: 60px;
}

.form {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    margin-bottom: 60px;
}

.form, .form input, .form button {
    margin-bottom: 10px;
    font-size: 2rem;
}

.doors {
    align-self: stretch;
    display: flex;
    justify-content: space-around;
    flex-wrap: wrap;
}

</style>