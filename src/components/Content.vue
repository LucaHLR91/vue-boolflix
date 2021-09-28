<template>
    <div class="content">
        <div class="cover front-content">
            <img v-if="info.poster_path" :src="`https://image.tmdb.org/t/p/w342${info.poster_path}`" :alt="info.title ? info.title : info.name">
            <img v-else src="`https://www.altavod.com/assets/images/poster-placeholder.png`" alt="cover">
        </div>
        <ul v-if="info.title" class="back-content">
            <li>{{info.title}}</li>
            <li>{{info.original_title}}</li>
            <li v-if="isFlagAvaliable('../assets/img/Flags/' + info.original_language + '.png')"><img :src="require('../assets/img/Flags/' + info.original_language + '.png')" alt="Nd">{{info.original_language}}</li>
            <li v-else>{{info.original_language}}</li>
            <li><i v-for="n in 5" :key="n" class="fa-star" :class="(n <= getStar()) ? 'fas' : 'far'"></i></li>
        </ul>
        <ul v-else class="back-content">
            <li>{{info.name}}</li>
            <li>{{info.original_name}}</li>
            <li v-if="isFlagAvaliable('../assets/img/Flags/' + info.original_language + '.png')"><img :src="require('../assets/img/Flags/' + info.original_language + '.png')" alt="Nd">{{info.original_language}}</li>
            <li v-else>{{info.original_language}}</li>
            <li><i v-for="n in 5" :key="n" class="fa-star" :class="(n <= getStar()) ? 'fas' : 'far'"></i></li>
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
        getStar() {
            return Math.ceil(this.info.vote_average / 2)
        }
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
        padding: 20px;


        .cover {
            width: 100%;
        }

        .cover img {
            width: 100%;
        }

        ul {
            display: none;
            list-style: none;
            background-color: rgba(0, 0, 0, 0.7);
            width: 100%;
            height: 100%;
            padding: 0;
            margin: 0;
            color: white;
            text-align: center;
            font-weight: 700;

            li {
                margin-top: 5px;
            }

            li i {
                color: gold;
                cursor: pointer;
            }
            
            img {
                width: 1vw;
                height: 1vw;
            }
        }
    }

    .content:hover .back-content {
        display: block;
        animation: fade-in 2s;
    }

    @keyframe fade-in {
        from { opacity: 1; }
        to { opacity: 0; }
    }

    .content:hover .front-content {
        display: none;
        
    }


</style>