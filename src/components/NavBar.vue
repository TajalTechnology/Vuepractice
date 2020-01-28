<template>
    <nav>

        <div>
        <ul>
            <li><a href="#">Home</a></li> &nbsp;
            <li><a href="#">About</a></li> &nbsp;
            <li><a href="#">Contact</a></li> &nbsp;


        </ul>

    </div>
    </nav>

    
</template>

<script>
    export default {
        name: "NavBar"
    }
</script>

<style scoped>
      nav{
        text-align:center ;
    }
    nav ul{
        padding: 0;
    }
    nav li{
        display: inline-block;
        list-style-type: none;
        margin: 0;
    }


</style>