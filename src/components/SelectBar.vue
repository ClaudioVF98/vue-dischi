<template>
    <div>
        <label for="genres">Choose a genre:</label>
        <select id="genres" name="genres" v-model="key" @change="$emit('search', key)">
            <option value="rock">Rock</option>
            <option value="pop">Pop</option>
            <option value="jazz">Jazz</option>
            <option value="metal">Metal</option>
        </select>

    </div>
</template>

<script>
export default {
    name: "SelecthBar",
    data(){
        return {
            key: "",
        }
    }
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
    label {
        color: white;
    }
</style>