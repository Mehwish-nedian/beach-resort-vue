<template>

    <div class="services__item">
        <slot class="icon" name="icon"></slot>
        <h2 class="services__subheading"><slot name="heading"></slot></h2>
        <p class="services__text"><slot name="text"></slot></p>
    </div>

</template>



<style lang="scss" scoped>

    .services{
        
        &__item>*:not(:last-child){
            margin-bottom: 1.5rem;
        }
        &__subheading{
            font-size: 2rem;
            font-weight: bold;
            letter-spacing: .2rem;
            
        }
        
        
    }
</style>