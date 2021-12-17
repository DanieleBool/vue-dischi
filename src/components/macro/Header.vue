<template>
    <header>
        <!-- <div class=""> -->
            <Logo/>
        <!-- </div> -->
    </header>
</template>

<script>
import Logo from '../commons/Logo.vue';

export default {
    name: 'Header',
    components: {
        Logo,
    }
}
</script>

<style lang="scss" scoped>
@import '../../assets/style/global.scss';
    header{
        background-color: $softBlue;
        height: 100%;
    }
</style>