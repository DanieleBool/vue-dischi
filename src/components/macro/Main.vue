<template>
    <main>
        <AlbumList/>
    </main>
</template>

<script>
import AlbumList from '../sections/AlbumList.vue';

export default {
  name: 'Main', 
  components: {
    AlbumList,
  }
}
</script>

<style lang="scss" scoped>
// @import '../../assets/style/global.scss';

</style>