<template>
    <div class="tabs">
        <div class="tabs__menu container">
            <div class="tabs__menu-before"></div>
            <div class="tabs__menu-items">
                <a href="#" class="tabs__menu-item" v-bind:class="{ 'tabs__menu-item--active': item.active }" v-for="(item, index) in tabs" :key="index">{{item.title}}</a>
            </div>
            <div class="tabs__menu-after"></div>
        </div>
        <div class="tabs__content container">
            <div class="tabs__content-before"></div>
            <div class="tabs__content-menu">
                <a class="tabs__content-menu-item" v-bind:class="{ 'tabs__content-menu-item--active': item.active }" v-for="(item, index) in menu" :key="index">{{item.title}}</a>
            </div>
            <div class="tabs__content-inner">

            </div>
            <div class="tabs__content-company">
                <h3 class="tabs__content-company-title">Базовые предприятия</h3>
                <img :src="require('../assets/img/'+item.img)" :alt="item.title" class="tabs__content-company-logo" v-for="(item, index) in logos" :key="index">
            </div>
            <div class="tabs__content-after"></div>
        </div>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                tabs: [
                    {title: 'Проект', active: true},
                    {title: 'Решения', active: false},
                    {title: 'Экспертное мнение', active: false},
                    {title: 'Рынок', active: false}
                ],
                menu: [
                    {title: 'Общие сведения', active: true},
                    {title: 'Преимущества', active: false},
                    {title: 'Характеристики', active: false},
                    {title: 'Экономическая эффективность', active: false},
                    {title: 'Документы', active: false}
                ],
                logos: [
                    {title: 'tvel', img: 'tvel.png'},
                    {title: 'rosatom', img: 'rosatom.png'},
                    {title: 'nzhk', img: 'nzhk.png'},
                    {title: 'centertech', img: 'centertech.png'},
                    {title: 'ensol', img: 'ensol.png'},
                    {title: 'suhe', img: 'suhe.png'},
                    {title: 'avl', img: 'avl.png'},
                    {title: 'cleanenergy', img: 'cleanenergy.png'},
                    {title: 'global', img: 'global.png'}
                ]
            }
        },
    }
</script>

<style lang="scss" scoped>
.tabs {
    &__menu {
        background: #ffffff;
        margin: 0 0 20px;
        &-items {
            padding: 35px 0 37px;
            display: flex;
        }
        &-item {
            position: relative;
            font-size: 16px;
            line-height: 14px;
            letter-spacing: 0.03em;
            text-transform: uppercase;
            font-weight: 600;
            text-decoration: none;
            color: rgba(48, 46, 74, 0.6);
            &:not(:last-child) {
                margin: 0 80px 0 0;
            }
            &--active {
                color: #302E4A;
                &::after {
                    content: '';
                    position: absolute;
                    width: 100%;
                    height: 2px;
                    background: #00A7F8;
                    left: 0;
                    bottom: -3px;
                }
            }
        }
    }
    &__content {
        display: grid;
        grid-template-columns: auto 305px 738px 197px auto;
        grid-template-rows: auto;
        grid-column-gap: 20px;
        grid-row-gap: 0px;
        margin-bottom: 40px;

        &-menu {
            padding: 22px 32px 32px;
            background: #FFFFFF;
            border-radius: 5px;
            display: flex;
            flex-direction: column;
            align-self: start;

            &-item {
                font-size: 16px;
                line-height: 24px;
                letter-spacing: 0.03em;
                color: rgba(48, 46, 74, 0.6);
                cursor: pointer;
                &:not(:last-child) {
                    margin: 0 0 20px;
                }
                &--active {
                    color: #302E4A;
                    font-weight: bold;
                }
            }
        }

        &-inner {
            padding: 30px 35px 18px;
            background: #FFFFFF;
            border-radius: 5px;
            align-self: start;
        }

        &-company {
            padding: 20px 24px 30px;
            background: #FFFFFF;
            border-radius: 5px;
            text-align: center;
            align-self: start;

            &-title {
                margin: 0 0 23px;
            }

            &-logo {
                &:not(:last-child) {
                    margin: 0 0 45px;
                }
            }
        }
    }
}
</style>