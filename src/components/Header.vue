<template>
    <header class="d-flex flex-row justify-content-between">
        <div id="logo">
            <img src="../assets/img/Netflix-Logo.png" alt="Netflix Logo">
        </div>
        <div class="search">
            <form action="">
                <input type="text">
            </form>
        </div>
    </header>
</template>

<script>

export default {
    name: 'Header'
}
</script>

<style lang="scss">
@import '../style/General';
@import 'bootstrap';

    header {
        background-color: black;
        height: 70px;

        #logo {
            height: 100%;
        }

        #logo img {
            width: 70px;
            
        }
    }
</style>