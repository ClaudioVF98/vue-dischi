<template>
    <main>
        <div id="card_container">
            <MusicCard 
                v-for="(item, i) in musicCds"
                :key="i"
                :musicObject="item"
            />
        </div>
    </main>
</template>

<script>
import MusicCard from './MusicCard.vue'
import axios from "axios"

export default {
    name: "MyMain",
    components: {
        MusicCard
    },
    data() {
        return {
            apiUrl: "https://flynn.boolean.careers/exercises/api/array/music",
            musicCds: []
        }
    },
    created() {
        this.getMusic();
    },
    methods: {
        getMusic() {
            axios
                .get(this.apiUrl)
                .then((result) => {
                    this.musicCds = result.data.response;
                })
                .catch((error) => {
                    console.log("Errore", error)
                })
        }
    },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
main {
    background-color: #1e2d3b;
    padding: 30px 50px;

    #card_container {
        display: flex;
        flex-wrap: wrap;
        margin: auto;
    }
}
</style>
