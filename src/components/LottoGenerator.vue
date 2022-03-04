<template>
    <div class="container">
        <img src="../assets/pcso-lotto-icon.png" alt="pcso-lotto-logo">
        <p>My Lotto Generator</p>
    </div>
    <button @click="generate()">Generate Numbers</button>
    
    <div class="container1">
        <div class="output" v-for="digit in randomDigits" :key="digit">
            {{ digit }}
        </div>
    </div>
</template>


<script>
export default {
    data() {
        return {
            randomDigits : [],
            isPlaying : false
        }
    },
    methods: {
        generate(){

            while(this.randomDigits.length < 6){
                let digits = Math.floor((Math.random() * 41)) + 1;
                if(!this.randomDigits.includes(digits)){
                    this.randomDigits.push(digits);
                }
            }
        }
    }
}
</script>

<style scoped>
p {
    font-size: 40px;
    font-family: sans-serif;
}
.container{
    display: flex;
    align-items: center;
    justify-content: center;
}
.container1{
    display: flex;
    margin-left: 26%;
    margin-right: 50%;
}
img{
    height: 100px;
    padding: 2px;
}

button{
    margin-bottom: 0px;
    margin-top: 20px;
    font-family: sans-serif;
    width: 320px;
    border-radius: 7px;
    box-shadow: 0px 5px 4px 2px #888888;
    height: 70px;
    font-size: 20px;
    margin-left: 43%;
    margin-right: 50%;
}

.output {
    padding: 24px;
    font-size: 80px;
    font-family: sans-serif;
}

</style>