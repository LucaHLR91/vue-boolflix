<template>
    <div class="content">
        <ul v-if="info.title">
            <li>{{info.title}}</li>
            <li>{{info.original_title}}</li>
            <li v-if="isFlagAvaliable('../assets/img/Flags/' + info.original_language + '.png')"><img :src="require('../assets/img/Flags/' + info.original_language + '.png')" alt="Nd">{{info.original_language}}</li>
            <li v-else>{{info.original_language}}</li>
            <li>{{info.vote_average}}</li>
        </ul>
        <ul v-else>
            <li>{{info.name}}</li>
            <li>{{info.original_name}}</li>
            <li v-if="isFlagAvaliable('../assets/img/Flags/' + info.original_language + '.png')"><img :src="require('../assets/img/Flags/' + info.original_language + '.png')" alt="Nd">{{info.original_language}}</li>
            <li v-else>{{info.original_language}}</li>
            <li>{{info.vote_average}}</li>
        </ul>
    </div>
</template>

<script>
export default {
    name: 'Content',
    props: ['info'],
    data() {
        return {
            FlagsAvaliable: [
                '../assets/img/Flags/de.png',
                '../assets/img/Flags/en.png',
                '../assets/img/Flags/es.png',
                '../assets/img/Flags/fr.png',
                '../assets/img/Flags/it.png',
                '../assets/img/Flags/ja.png'  
            ],
        }
    },
    methods: {
        isFlagAvaliable(language) {
            return this.FlagsAvaliable.includes(language)    
        },
    }
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
            display: flex;
            flex-direction: column;
            align-items: flex-start;
            
            img {
                width: 1vw;
                height: 1vw;
            }
        }

    }

</style>