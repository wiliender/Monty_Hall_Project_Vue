<template>
    <div id="app">
        <h1>Problema de Monty Hall</h1>
        <Door number="1" :hasGift="false" /><!-- : para passar o segundo parametro falso como boolean, sem os : passa como string -->
    </div>
</template>

<script>
import Door from "./components/Door";
export default {
    nome: "App",
    components: {
        Door
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
</style>