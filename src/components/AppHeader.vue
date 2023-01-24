<script>
export default {
   name: 'AppHeader' 
}
</script>

<template>
    <header class="d-flex justify-content-center align-items-center container">
        <div class="comands">
            <div class="main-button"></div>
            <div class="secondary-button bg-red"></div>
            <div class="secondary-button bg-yelow"></div>
            <div class="secondary-button bg-green"></div>
        </div>
        <div class="logo">
            <img class="img-fluid" src="https://upload.wikimedia.org/wikipedia/commons/thumb/9/98/International_Pok%C3%A9mon_logo.svg/2560px-International_Pok%C3%A9mon_logo.svg.png" alt="">
        </div>
    </header>
</template>

<style lang="scss">
header{
    height: 200px;
    
    .comands{
        display: flex;
        width: 50%;
        height: 80%;
        .main-button{
            height: 100px;
            width: 100px;
            border-radius: 50%;
            background-color: #A1A6FF;
            border: 5px solid #fff;
        }
        .secondary-button{
            margin-left: 1rem;
            width: 50px;
            height: 50px;
            border-radius: 50%;
            border: 5px solid #fff;
            
        }
    }
    
    .bg-red{
        background-color: #FF8276;
    }
    .bg-yelow{
        background-color: #FCF6A6;
    }
    .bg-green{
        background-color: #63A466;
    }
    .logo{
        width: 50%;
        
        display: flex;
        justify-content: flex-end;
        align-items: center;
        img{
            width: 200px;
        }
    }
}

</style>