<template>
    <header class="d-flex flex-row justify-content-between">
        <div id="logo">
            <img src="../assets/img/Netflix-Logo.png" alt="Netflix Logo">
        </div>
        <div class="search">
            <input type="text" placeholder="Cerca Il Tuo Film">
            <button class="btn_search">Cerca</button>
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


    header {
        background-color: black;
        height: 70px;

        #logo {
            display: flex;
            align-items: center;
            height: 100%;
            margin-left: 10px;
        }

        #logo img {
            width: 100px;
            
        }

        .search {
            display: flex;
            align-items: center;
            height: 100%;
            margin-right: 10px;

            input {
                border-radius: 5px;
                border: none;
                margin-right: 5px;
            }

            .btn_search {
                color: white;
                background-color: red;
                border: none;
                border-radius: 5px;
                margin-right: 10px;
                padding: 0 5px;
            }
        }
    }
</style>