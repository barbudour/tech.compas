<template>
    <div class="container title">
        <div class="title__before"></div>
        <div class="title__container">
            <a href="#" class="title__category">
                Технология
            </a>
            <h1 class="title__heading--main">
                Литий-ионные накопители энергии
            </h1>
            <h3 class="title__heading--sub">
                Технологии и&nbsp;продукции не&nbsp;ядерного назначения
            </h3>
        </div>
        <div class="title__after"></div>
    </div>
</template>

<script>
    export default {
        
    }
</script>

<style lang="scss" scoped>
.title {
    background: #ffffff;
    padding: 38px 0 32px;
    &__container {
        display: flex;
        justify-content: center;
        flex-direction: column;
        text-align: center;
    }
    &__category {
        font-size: 14px;
        line-height: 14px;
        letter-spacing: 0.03em;
        text-transform: uppercase;
        color: #00A7F8;
        margin: 0 0 -1px;
        text-decoration: none;
        font-weight: bold;
    }
    &__heading {
        &--main {
            font-size: 37px;
            line-height: 40px;
            color: #302E4A;
            margin: 0;
        }
        &--sub {
            font-size: 16px;
            line-height: 24px;
            font-weight: normal;
            color: rgba(48, 46, 74, 0.8);
            margin: 0;
        }
    }
}
</style>