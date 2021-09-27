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
    
}
</script>

<style lang="scss">
@import '../style/General';
</style>