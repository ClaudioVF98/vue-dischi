<template>
    <main>
        <div>
            <SelectBar @search="swapGenre"/>
        </div>
        <div id="card_container">
            <MusicCard v-for="(item, i) in filteredCds" :key="i" :musicObject="item" />
        </div>
    </main>
</template>

<script>
import SelectBar from './SelectBar.vue'
import MusicCard from './MusicCard.vue'
import axios from "axios"

export default {
    name: "MyMain",
    components: {
        MusicCard,
        SelectBar
    },
    data() {
        return {
            apiUrl: "https://flynn.boolean.careers/exercises/api/array/music",
            musicCds: [],
            activeGenre: "all"
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
        },
        swapGenre(key) {
            this.activeGenre=key
        }
    },
    computed: {
        filteredCds() {
            if (this.activeGenre === "all") {
                return this.musicCds;
            } else {
                return this.musicCds.filter(item => {
                    return item.genre.toLowerCase().includes(this.activeGenre);
                })
            }
        }
    }

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
main {
    background-color: #1e2d3b;
    padding: 30px 50px;

    .label-search {
        width: calc(100% / 5);
    }

    #card_container {
        display: flex;
        flex-wrap: wrap;
        margin: auto;
    }
}
</style>
