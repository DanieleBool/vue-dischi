<template>
    <div>
        <!-- ricerca per titolo -->
        <form class="d-flex" action="">
            <input v-model="searchArtist" class="form-control" type="text" placeholder="Search artist">
            <button class="btn btn-primary mx-3" @click.prevent="$emit('search', searchArtist)">Search</button>
            <button class="btn btn-warning" @click.prevent="$emit('reset', searchArtist), artistValue='', genreValue='' ">Reset</button>
        </form>
        <!-- ricerca per genere -->
        <select v-molde="genreValue" class="form-select my-2" name="" @change="$emit ('searchh', genreValue)">
            <option value="">Seleziona il genere</option>
            <option value="Pop">Pop</option>
            <option value="Rock">Rock</option>
            <option value="Jazz">Jazz</option>
            <option value="Metal">Metal</option>
        </select>
    </div>
</template>

<script>
export default {
    name: 'SearchBar',
    data() {
        return{
            searchArtist: '',
            genreValue: '',
        }
    },
}
</script>

<style lang="scsss" scoped>

</style>