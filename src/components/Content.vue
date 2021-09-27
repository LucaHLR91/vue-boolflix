<template>
    <div class="content">
        <ul>
            <li>{{info.title}}</li>
            <li>{{info.original_title}}</li>
            <li><img :src="require('../assets/img/Flags/' + info.original_language + '.png')" alt="Nd">{{info.original_language}}</li>
            <li>{{info.vote_average}}</li>
        </ul>
    </div>
</template>

<script>
export default {
    name: 'Content',
    props: ['info'],
    
}
</script>

<style lang="scss">
@import '../style/General';

    .content {
        display: flex;
        flex-direction: column;
        align-items: flex-start;
        width: calc(100% / 6);
        background-color: rgba(0, 0, 0, 0.5);
        padding: 20px;

        ul {
            list-style: none;
            
            img {
                width: 1vw;
                height: 1vw;
            }
        }

    }

</style>