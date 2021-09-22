<template>
    <div class="featured-room">
        <img @click="gotoRoom" :src="require('../assets/images/'+image)" alt="room-image" class="featured-room__image">
        <button v-bind:class="{'featured-room__title--small': small, 'featured-room__title': true}">{{title}}</button>
        <div class="featured-room__price-tag">{{price}}<div>per night</div></div>
    </div>
</template>
<script>
export default {
    props: ['id','image', 'title', 'price', 'small'],
    methods: {
        gotoRoom(){
            this.$router.push('/rooms/'+this.id);
        }
    }
    
}

</script>
<style lang="scss" scoped>
    .featured-room{
        text-align: center;
        width: 40rem;
        position: relative;
        width: 100%;
        box-shadow: 0 2rem 5rem rgba(0,0,0,.3);
        border-right: 2px solid black;
       
        &__image{
           max-width: 100%;
           height: auto;  
           overflow: hidden;         
        }
        &__title{
            font-size: 2rem;
            letter-spacing: .5rem;
            width: 100%;
            position: absolute;
            bottom: 0;
            left: 0;
            background-color: $color-secondary;
            color: #fff;
            padding: 1rem;
            border: none;
            border-bottom: 2px solid black;
        }
        &__title--small{
            font-size: 1.2rem;
            padding: .5rem;
        }
        &__price-tag{
            position: absolute;
            top: 0;
            left: 0;
            background-color: black;
            color: #fff;
            font-size: 2rem;
            width: 7rem;
            line-height: 1;
            padding: 0.4rem 1rem;
            border-bottom-right-radius: 1rem;
            letter-spacing: .2rem;
            div{
                font-size: 1rem;
                letter-spacing: 0;
            }
        }
    }
</style>