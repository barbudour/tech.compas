<template>
    <div class="intro container">
        <div class="intro__before"></div>
        <div class="intro__container">
            <div class="intro__slider">
                <div class="intro__slider-main">
                    <carousel v-if="isNuxtReady" :items='1' :nav='false' :dots='false'>
                        <img src="https://placeimg.com/708/398/tech" alt="">
                        <img src="https://placeimg.com/708/398/tech" alt="">
                        <img src="https://placeimg.com/708/398/tech" alt="">
                        <img src="https://placeimg.com/708/398/tech" alt="">
                        <img src="https://placeimg.com/708/398/tech" alt="">
                        <img src="https://placeimg.com/708/398/tech" alt="">
                        <img src="https://placeimg.com/708/398/tech" alt="">
                        <img src="https://placeimg.com/708/398/tech" alt="">
                        <img src="https://placeimg.com/708/398/tech" alt="">
                        <img src="https://placeimg.com/708/398/tech" alt="">
                    </carousel>
                </div>
                <div class="intro__slider-small">
                    <carousel v-if="isNuxtReady" :margin='10' :items='8' :nav='false' :dots='false'>
                    <img src="https://placeimg.com/80/80/tech" alt="">
                    <img src="https://placeimg.com/80/80/tech" alt="">
                    <img src="https://placeimg.com/80/80/tech" alt="">
                    <img src="https://placeimg.com/80/80/tech" alt="">
                    <img src="https://placeimg.com/80/80/tech" alt="">
                    <img src="https://placeimg.com/80/80/tech" alt="">
                    <img src="https://placeimg.com/80/80/tech" alt="">
                    <img src="https://placeimg.com/80/80/tech" alt="">
                    <img src="https://placeimg.com/80/80/tech" alt="">
                    <img src="https://placeimg.com/80/80/tech" alt="">
                    </carousel>
                </div>
            </div>
            <div class="intro__info">
                <div class="intro__info-item">
                    <h3 class="intro__info-title">Направление</h3>
                    <div class="intro__info-wrapper">
                        <ul class="intro__info-directions">
                            <li class="intro__info-direction" v-for="(item, index) in directions" :key="index" :style="'margin-left:'+index*32+'px'">{{item.title}}</li>
                        </ul>
                    </div>
                </div>
                <div class="intro__info-item">
                    <h3 class="intro__info-title">Сферы применения</h3>
                    <div class="intro__info-wrapper">
                        <ul class="intro__info-areas">
                            <li class="intro__info-area" v-for="(item, index) in areas" :key="index">{{item.title}}</li>
                        </ul>
                    </div>
                </div>
                <div class="intro__info-tags">
                    <a href="#" class="intro__info-tag" v-for="(item, index) in tags" :key="index">{{item.title}}</a>
                </div>
            </div>
        </div>
        <div class="intro__after"></div>
    </div>
</template>

<script>
    const carousel = () => window && window !== undefined ? import("vue-owl-carousel") : null;
    export default {
        components: {
            carousel,
        },
        data() {
            return {
                isNuxtReady: false,
                directions: [
                    {title: 'Технологии и продукции не ядерного назначения'},
                    {title: 'Накопители энергии'},
                    {title: 'Накопители ЛИА'}
                ],
                areas: [
                    {title: 'Транспорт'},
                    {title: 'Электроэнергетика'},
                    {title: 'Металлургия'},
                    {title: 'Промышленность'},
                    {title: 'Авиастроение'},
                    {title: 'Системы телекоммуникации'}
                ],
                tags: [
                    {title: 'Аккумулятор'},
                    {title: 'Химический источник тока'},
                    {title: 'Росатом'},
                    {title: 'Электро-транспорт'},
                    {title: 'ТВЭЛ'}
                ]
            }
        },
        mounted () {
            const vm = this;
            if (process.browser) {
                window.onNuxtReady(app => {
                console.log("Nuxt ready!");
                vm.isNuxtReady = true;
                });
            };
        },
    }
</script>

<style lang="scss" scoped>
.intro {
    padding: 30px 0 40px;
    &__container {
        display: grid;
        grid-template-columns: 708px 522px;
        grid-template-rows: auto;
        grid-column-gap: 48px;
        grid-row-gap: 0px;
    }
    &__slider {
        &-main {
            border-radius: 5px;
            overflow: hidden;
            margin: 0 0 10px;
        }
        &-small {
            .owl-item {
                border-radius: 5px!important;
                overflow: hidden!important;
            }
        }
    }
    &__info {
        &-title {
            font-size: 20px;
            line-height: 29px;
            text-transform: uppercase;
            color: #302E4A;
            margin: 0 0 12px;
        }
        &-wrapper {
            padding: 20px 25px;
            background: #FFFFFF;
            border-radius: 5px;
            margin: 0 0 35px;
        }
        &-directions {
            list-style: none;
            padding: 0;
        }
        &-direction {
            position: relative;
            font-size: 18px;
            line-height: 27px;
            color: rgba(48, 46, 74, 0.8);
            &:not(:last-child) {
                margin-bottom: 6px;
            }
            &:not(:first-child)::before {
                content: '';
                position: absolute;
                left: -21px;
                top: -1px;
                width: 14px;
                height: 14px;
                border-left: 1.5px solid #00A7F8;
                border-bottom: 1.5px solid #00A7F8;
                border-radius: 0 0 0 3px;
            }
        }
        &-areas {
            display: grid;
            grid-template-columns: repeat(2, auto);
            grid-template-rows: repeat(auto);
            grid-column-gap: 25px;
            grid-row-gap: 11px;
            padding: 0;
            list-style: none;
        }
        &-area {
            position: relative;
            padding: 0 0 0 19px;
            font-size: 18px;
            line-height: 22px;
            color: rgba(48, 46, 74, 0.8);
            &::before {
                content: '';
                width: 5px;
                height: 5px;
                border-radius: 50%;
                background: #00A7F8;
                position: absolute;
                left: 0;
                top: 10px;
            }
        }
        &-tags {
            display: flex;
            flex-wrap: wrap;
        }
        &-tag {
            position: relative;
            padding: 2px 6px 3px 17px;
            font-size: 16px;
            line-height: 24px;
            color: #FFFFFF;
            background: #00A7F8;
            border-radius: 5px 0 0 5px;
            text-decoration: none;
            margin: 0 20px 10px 0;
            &::after {
                content: '';
                width: 11px;
                height: 29px;
                position: absolute;
                top: 0;
                left: 100%;
                background-image: url('~assets/svg/corner.svg');
            }
        }
    }
}
</style>