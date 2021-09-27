<template>
    <ul>
        <li>{{info.title}}</li>
        <li>{{info.original_title}}</li>
        <li><img :src="require('../assets/img/Flags/' + info.original_language + '.png')" :alt="Nd">{{info.original_language}}</li>
        <li>{{info.vote_average}}</li>
    </ul>
</template>

<script>
export default {
    name: 'Content',
    props: ['info'],
    
}
</script>

<style lang="scss">
@import '../style/General';

    ul {
        img {
            width: 1vw;
            height: 1vw;
        }
    }
</style>