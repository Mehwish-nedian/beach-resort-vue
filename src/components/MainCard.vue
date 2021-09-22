<template>
    <div class="container">
        <h1 class="main-heading"><slot  name="heading"></slot></h1>
        <hr>
        <h6 class="sub-heading"><slot name="sub-heading"></slot></h6>

        <base-button  :goto=goto ><slot name="btn-text"></slot></base-button>
    </div>
</template>
<script>
import BaseButton from './BaseButton.vue';
export default {
    props: ['goto'],
    components:{
        BaseButton
    }
}
</script>
<style lang="scss" scoped>
$white-color: #fff;
.container{
    display: flex;
    flex-direction: column;
    background-color: rgba(0,0,0,.3);
    text-align: center;
    justify-content: center;
    align-items: center;
    color: $white-color;
    padding: 2rem 1rem;
    width: 70%;
}
.container>*{
    margin-bottom: 1.5rem;
}


.main-heading{
    font-size: 5rem ;    
}
 @media only screen and (max-width: 600px){
       .main-heading{
            font-size: 3rem ;    
        } 
}


</style>