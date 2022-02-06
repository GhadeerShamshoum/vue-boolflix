<template>
    <nav>
        <ul class="menu">
            <li>Home</li>
            <li>Serie TV</li>
            <li>Film</li>
            <li>Original</li>
            <li>Aggiunti di recente</li>
            <li>La mia lista</li>
        </ul>
        
    </nav>
 
</template>

<script>


export default {
  name: 'Menu',
  
}

</script>

<style lang="scss" >
.menu{
    list-style: none;
    display: flex;
    margin: 0 50px;
    li{
        color: white;
        padding: 0 5px;
        font-weight: 200;
    }
}

</style>
