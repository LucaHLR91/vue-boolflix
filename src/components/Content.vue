<template>
    <ul>
        <li>{{info.title}}</li>
        <li>{{info.original_title}}</li>
        <li>{{info.original_language}}</li>
        <li>{{info.vote_average}}</li>
    </ul>
</template>

<script>
export default {
    name: 'Content',
    props: ['info'],
    data() {
        return {
            flags: [
                '../assets/img/flags/ItalianFlag.png',
                '../assets/img/flags/AmericanFlag.png',
                '../assets/img/flags/DeutchFlag.jpg',
                '../assets/img/flags/FrenchFlag.png',
                '../assets/img/flags/JapaneseFlag.png',
                '../assets/img/flags/SpanishFlag.png',
            ]
        }
    }
}
</script>

<style lang="scss">
@import '../style/General';
</style>