<template>
    <div class="tabs">
        <div class="tabs__menu container">
            <div class="tabs__menu-before"></div>
            <div class="tabs__menu-items">
                <a @click="changeTab(item)" class="tabs__menu-item" :data-tab="item.alias" v-bind:class="{ 'tabs__menu-item--active': item.active }" v-for="(item, index) in tabs" :key="index">{{item.title}}</a>
            </div>
            <div class="tabs__menu-after"></div>
        </div>
        <div class="tabs__content container">
            <div class="tabs__content-before"></div>
            <div class="tabs__content-menu" v-if="activeTab === 'project'">
                <a class="tabs__content-menu-item" @click='scrollTo()' :data-item='item.alias' v-bind:class="{ 'tabs__content-menu-item--active': item.active }" v-for="(item, index) in menu" :key="index">{{item.title}}</a>
            </div>
            <div class="tabs__content-menu" v-if="activeTab === 'solutions'">
                <a class="tabs__content-menu-item" @click='scrollTo()' :data-item='item.alias' v-bind:class="{ 'tabs__content-menu-item--active': item.active }" v-for="(item, index) in menu2" :key="index">{{item.title}}</a>
            </div>
            <div class="tabs__content-inner">
                <div class="tabs__content-project content" id="project" v-if="activeTab === 'project'">
                    <h2 data-menu="all" v-observe-visibility="visibilityChanged">Общие сведения</h2>
                    <p>Считается, что ближайшее будущее автотранспорта — переход на электротягу, а будущее электросетей — переход на «умный» режим работы, при котором исчезнет необходимость постоянно уравнивать объемы производства и потребления. Оба перехода невозможны без внедрения эффективных накопителей энергии. Одним из перспективных решений являются литий-ионные накопители энергии.</p>
                    <img src="~assets/img/project-1.jpg" alt="">
                    <p>Оба перехода невозможны без внедрения эффективных накопителей энергии. Одним из перспективных решений являются литий-ионные накопители энергии.</p>
                    <img src="~assets/img/project-2.jpg" alt="">
                    <div class="advantages">
                        <h2 data-menu="advantages" v-observe-visibility="visibilityChanged">Преимущества</h2>
                        <div class="advantages-item">
                            <div class="advantages-item-icon">
                                <img src="~assets/svg/clock.svg?data" />
                            </div>
                            <div class="advantages-item-text">
                                <h3>УВЕЛИЧЕННОЕ ВРЕМЯ РАБОТЫ</h3>
                                <p>Литий-ионные накопители энергии не требуют дополнительного обслуживания и чистки и работают дольше своих свинцово-кислотных аналогов – до 9 часов непрерывной работы.</p>
                            </div>
                        </div>
                        <div class="advantages-item">
                            <div class="advantages-item-icon">
                                <img src="~assets/svg/battery.svg?data" />
                            </div>
                            <div class="advantages-item-text">
                                <h3>БЫСТРАЯ ЗАРЯДКА</h3>
                                <p>Литий-ионные аккумуляторы заряжаются гораздо быстрее. Полная зарядка занимает от 2-х часов, против 8-ми у свинцово-кислотных аккумуляторов.</p>
                            </div>
                        </div>
                        <div class="advantages-item">
                            <div class="advantages-item-icon">
                                <img src="~assets/svg/money.svg?data" />
                            </div>
                            <div class="advantages-item-text">
                                <h3>СНИЖЕНИЕ РАСХОДОВ</h3>
                                <p>Уменьшение времени заряда несомненно положительно скажется на снижении расходов. В среднем переход на литий-ионные накопители энергии, может на 17% увеличить доход в результате снижения времени простоя, окупаемость таким образом составляет всего 10-13 месяцев.</p>
                            </div>
                        </div>
                        <div class="advantages-item">
                            <div class="advantages-item-icon">
                                <img src="~assets/svg/gears.svg?data" />
                            </div>
                            <div class="advantages-item-text">
                                <h3>УЛУЧШЕНИЕ ПРОИЗВОДИТЕЛЬНОСТИ</h3>
                                <p>Многие отмечают возросшую силу грузоподъемника в результате перехода на литий-ионные накопители энергии. Что происходит за счет меньшего износа литий-ионных батарей в отличии от альтернативных.</p>
                            </div>
                        </div>
                    </div>
                    <img src="~assets/svg/table.svg?data" alt="" class="table">
                    <div class="characteristics">
                        <h2 data-menu="characteristics" v-observe-visibility="visibilityChanged">Характеристики</h2>
                        <div class="characteristics-item">
                            <h3>НАПРЯЖЕНИЕ</h3>
                            <p>24 – 80 В (широко используемые типы накопителей. Возможна поставка накопителей с напряжением вне указанного диапазона)</p>
                        </div>
                        <div class="characteristics-item">
                            <h3>ЁМКОСТЬ</h3>
                            <p>40, 60, 90, 100, 140, 160, 200, 260, 300, 400, 700, 1000 (А*ч)</p>
                        </div>
                        <div class="characteristics-item">
                            <h3>ГАБАРИТНЫЕ РАЗМЕРЫ</h3>
                            <p>Габаритные размеры накопителя совпадают с габаритными размерами используемой традиционно АБ.</p>
                        </div>
                        <div class="characteristics-item">
                            <h3>МАССА</h3>
                            <p>Масса ЛИА меньше массы традиционной АБ более чем в 2 раза. Для электропогрузчиков используются специальный комплект догруза.</p>
                        </div>
                    </div>
                    <h2 data-menu='economy' v-observe-visibility="visibilityChanged">Экономическая эффективность</h2>
                    <h3>Срок окупаемости от 1 года</h3>
                    <p>Срок окупаемости и экономический эффект зависят от ряда параметров: тип аккумуляторной батареи, интенсивности эксплуатации транспортного средства, наличия и объема обменного фонда аккумуляторных батарей.</p>
                    <img class="charts" src="~assets/svg/charts.svg?data" alt="">
                    <h3>В среднем стоимость владения за 10 лет накопителями ЛИНЭТ ниже на 10,74 млн. руб.</h3>
                    <img class="chart" src="~assets/svg/chart.svg?data" alt="">
                </div>
                <div class="tabs__content-solutions content" id="solutions" v-if="activeTab === 'solutions'">
                    <h2 data-menu='system' v-observe-visibility="visibilityChanged2">Системы накопления энергии</h2>
                    <p class="lead">Преимущества использования ЛИАБ в СОПТ по сравнению с традиционными СКАБ</p>
                    <ul>
                        <li>Высокая энергоемкость. ЛИА может отдать 100% емкости не более чем за 1 час. СКАБ - за 10 часов и более.</li>
                        <li>Возможность обеспечения высоких разрядных токов. Максимальная величина допустимого толчкового тока разряда для ЛИА равна 3С, для СКАБ не более 1,5С.</li>
                        <li>Отсутствие необходимости создания микроклимата в помещении. Широкий температурный диапазон эксплуатации от -45°C до +85°C.</li>
                        <li>Нет необходимости искусственной вентиляции.</li>
                        <li>ЛИАБ пожаробезопасны.</li>
                        <li>Минимальное воздействие на окружающую среду. Исключены возможности утечки электролита, корпус полностью герметичен.</li>
                        <li>Простота обслуживания, возможность дистанционного мониторинга состояния каждого элемента батареи.</li>
                        <li>Срок эксплуатации в энергетике — до 30 лет.</li>
                    </ul>
                    <h3>Реализованный проект по переоснащению сопт гпп-2 на предприятии</h3>
                    <div class="price">
                        <h4>Характеристики пилотной установки:</h4>
                        <ul class="price__list">
                            <li class="price__list-item">энергоемкость батареи 90 кВтч;</li>
                            <li class="price__list-item">шкаф ввода АБ на ток 400 А;</li>
                            <li class="price__list-item">ёмкость элементов ЛИА 480 Ач;</li>
                            <li class="price__list-item">два основных ЗВУ на 100А;</li>
                            <li class="price__list-item">комплекс из 4-х шкафов с ЛИА и BMS;</li>
                            <li class="price__list-item">два дополнительных ЗВУ на 40А;</li>
                        </ul>
                        <div class="price__total">
                            <div class="price__total-sub">
                                Cтоимость:
                            </div>
                            <div class="price__total-sum">
                                6,75 млн. руб.
                            </div>
                        </div>
                    </div>
                    <div class="result">
                        <h4>Результаты:</h4>
                        <ul>
                            <li>значительное снижение капитальных</li>
                            <li>затрат за счёт применения ЛИА меньшей мощности;</li>
                            <li>снижение издержек на обслуживание АБ СОПТ;</li>
                            <li>вывод из эксплуатации зарядных комнат.</li>
                        </ul>
                    </div>
                    <h2 data-menu='promtech' v-observe-visibility="visibilityChanged2">Промышленная техника</h2>
                    <h4>Типовые решения накопителей энергии на литий-ионных аккумуляторах</h4>
                    <carousel v-if="isNuxtReady" :margin='16' :items='3' :nav='false' :dots='false' class="slider">
                        <div class="product" v-for="(item, index) in products" :key="index">
                            <div class="product__title">{{item.title}}</div>
                            <div class="product__attr" v-for="(item, index) in item.attr" :key="index">
                                <span class="product__attr-title">{{item.title}}</span>
                                <span class="product__attr-value">{{item.value}}</span>
                            </div>
                        </div>
                        <template slot="prev"><img src="@/assets/svg/arrow-prev.svg?data" alt=""></template>
                        <template slot="next"><img src="@/assets/svg/arrow-next.svg?data" alt=""></template>
                    </carousel>
                    <p>*суммарная мощность тягового двигателя и двигателя подъема <br>
                    **указывается среднее время работы при 50% загруженности транспорта</p>
                    <ul>
                        <li>для различных применений можно увеличивать или уменьшать ёмкость накопителя;</li>
                        <li>увеличение ёмкости увеличивает время работы без подзаряда;</li>
                        <li>время заряда определяется зарядным устройством, в таблице показано использование бортовое зарядное устройство с питанием от бытовой сети 220 В;</li>
                        <li>для уменьшения времени заряда целесообразно использовать стационарное зарядное устройство с питанием от сети 380 В;</li>
                        <li>стоимость накопителя энергии для электропогрузчика увеличивается за счёт догруза.</li>
                    </ul>
                    <h2 data-menu='cityelectro' v-observe-visibility="visibilityChanged2">Городской электротранспорт</h2>
                    <p class="lead">Основные преимущества электробуса, как городского транспортного средства:</p>
                    <ul>
                        <li>Отсутствие вредных выхлопов в атмосферу</li>
                        <li>Низкие эксплуатационные расходы</li>
                        <li>Снижение общего шумового фона в городе</li>
                        <li>Повышенный комфорт для пассажиров за счет низкого уровня шума и вибрации в салоне</li>
                    </ul>
                    <h4>Комплект Li-ion накопителя энергии для городского электротранспорта:</h4>
                    <ul>
                        <li>Батарейные модули, состоящие из литий-ионных аккумуляторов, блоков управления аккумуляторами, блоков управления модулями (БУМ)</li>
                        <li>Система BMS</li>
                        <li>Бортовое зарядное устройство</li>
                        <li>Комплект соединительных жгутов</li>
                    </ul>
                    <h2 data-menu='spectech' v-observe-visibility="visibilityChanged2">Спец. техника</h2>
                    <h4>Система накопления энергии для работы спецтранспорта в условиях высоких температур и магнитных полей</h4>
                    <p>Для работы спецтранспорта в особых технологических условиях необходима установка СНЭ, которая будет функционировать в штатном режиме, независимо от внешних условий. Изготовлен опытный образец накопителя для эксплуатации парка внутризаводских электротранспортных средств в условиях высоких температур и магнитных полей.</p>
                    <h4>Система накопления энергии для горно-шахтного оборудования</h4>
                    <p>Погрузочно-доставочная машина (ПДМ) работает в сложных, горно-шахтных условиях, и система накопления энергии должна быть полностью приспособлена для работы в таких условиях. Установка систем накопления энергии на литий-ионных аккумуляторах в погрузочно-доставочные машины позволит снизить финансовые и временные затраты на обслуживание машины, существенно увеличить мобильность, а также производительность ПДМ.</p>
                </div>
                <div class="tabs__content-view content" id="view" v-if="activeTab === 'view'">
                    <h2>Раздел в разработке</h2>
                </div>
                <div class="tabs__content-market content" id="market" v-if="activeTab === 'market'">
                    <h2>Раздел в разработке</h2>
                </div>
            </div>
            <div class="tabs__content-company">
                <h3 class="tabs__content-company-title">Базовые предприятия</h3>
                <a :href="item.href" v-for="(item, index) in logos" :key="index" class="tabs__content-company-logo">
                    <img :src="require('../assets/img/'+item.img)" :alt="item.title">
                </a>
            </div>
            <div class="tabs__content-after"></div>
        </div>
    </div>
</template>

<script>
import Vue from 'vue'
import VueObserveVisibility from 'vue-observe-visibility'

Vue.use(VueObserveVisibility)

    const carousel = () => window && window !== undefined ? import("vue-owl-carousel") : null;
    export default {
        components: {
            carousel,
        },
        data() {
            return {
                isNuxtReady: false,
                activeTab: 'project',
                tabs: [
                    {title: 'Проект', active: true, alias: 'project'},
                    {title: 'Решения', active: false, alias: 'solutions'},
                    {title: 'Экспертное мнение', active: false, alias: 'view'},
                    {title: 'Рынок', active: false, alias: 'market'}
                ],
                menu: [
                    {title: 'Общие сведения', active: true, alias: 'all'},
                    {title: 'Преимущества', active: false, alias: 'advantages'},
                    {title: 'Характеристики', active: false, alias: 'characteristics'},
                    {title: 'Экономическая эффективность', active: false, alias: 'economy'},
                    // {title: 'Документы', active: false}
                ],
                menu2: [
                    {title: 'Системы накопления энергии', active: true, alias: 'system'},
                    {title: 'Пром. техника', active: false, alias: 'promtech'},
                    {title: 'Городской электротранспорт', active: false, alias: 'cityelectro'},
                    {title: 'Спец. техника', active: false, alias: 'spectech'}
                ],
                logos: [
                    {title: 'tvel', img: 'tvel.png', href: 'https://www.tvel.ru/'},
                    {title: 'rosatom', img: 'rosatom.png', href: 'https://www.rosatom.ru/'},
                    {title: 'nzhk', img: 'nzhk.png', href: 'http://www.nccp.ru/'},
                    {title: 'centertech', img: 'centertech.png', href: 'https://centrotech.ru/'},
                    {title: 'ensol', img: 'ensol.png', href: 'http://www.ensoltech.ru/'},
                    {title: 'suhe', img: 'suhe.png', href: 'http://xn--q1aeg6a.xn--p1ai/'},
                    {title: 'avl', img: 'avl.png', href: 'https://www.avl.com/'},
                    {title: 'cleanenergy', img: 'cleanenergy.png', href: 'https://clean-energy.ru/'},
                    {title: 'global', img: 'global.png', href: 'http://www.global-avtomatika.ru/'}
                ],
                products: [
                    {
                        title: 'Электротележка ЭК-1 2, ЭК-202',
                        attr: [
                            {
                                title: 'Потребляемая мощность*',
                                value: '1,5 кВт'
                            },
                            {
                                title: 'Рабочее напряжение',
                                value: '48 В'
                            },
                            {
                                title: 'Ёмкость накопителя',
                                value: '200 Ач'
                            },
                            {
                                title: 'Время заряда',
                                value: '4 ч'
                            },
                            {
                                title: 'Время работы**',
                                value: '5 ч'
                            }
                        ]
                    },
                    {
                        title: 'Электротележка ЭК-1 2, ЭК-202',
                        attr: [
                            {
                                title: 'Потребляемая мощность*',
                                value: '1,5 кВт'
                            },
                            {
                                title: 'Рабочее напряжение',
                                value: '48 В'
                            },
                            {
                                title: 'Ёмкость накопителя',
                                value: '200 Ач'
                            },
                            {
                                title: 'Время заряда',
                                value: '4 ч'
                            },
                            {
                                title: 'Время работы**',
                                value: '5 ч'
                            }
                        ]
                    },
                    {
                        title: 'Электротележка ЭК-1 2, ЭК-202',
                        attr: [
                            {
                                title: 'Потребляемая мощность*',
                                value: '1,5 кВт'
                            },
                            {
                                title: 'Рабочее напряжение',
                                value: '48 В'
                            },
                            {
                                title: 'Ёмкость накопителя',
                                value: '200 Ач'
                            },
                            {
                                title: 'Время заряда',
                                value: '4 ч'
                            },
                            {
                                title: 'Время работы**',
                                value: '5 ч'
                            }
                        ]
                    },
                    {
                        title: 'Электротележка ЭК-1 2, ЭК-202',
                        attr: [
                            {
                                title: 'Потребляемая мощность*',
                                value: '1,5 кВт'
                            },
                            {
                                title: 'Рабочее напряжение',
                                value: '48 В'
                            },
                            {
                                title: 'Ёмкость накопителя',
                                value: '200 Ач'
                            },
                            {
                                title: 'Время заряда',
                                value: '4 ч'
                            },
                            {
                                title: 'Время работы**',
                                value: '5 ч'
                            }
                        ]
                    },
                    {
                        title: 'Электротележка ЭК-1 2, ЭК-202',
                        attr: [
                            {
                                title: 'Потребляемая мощность*',
                                value: '1,5 кВт'
                            },
                            {
                                title: 'Рабочее напряжение',
                                value: '48 В'
                            },
                            {
                                title: 'Ёмкость накопителя',
                                value: '200 Ач'
                            },
                            {
                                title: 'Время заряда',
                                value: '4 ч'
                            },
                            {
                                title: 'Время работы**',
                                value: '5 ч'
                            }
                        ]
                    },
                ]
            }
        },
        methods: {
            changeTab(item) {
                let tab = event.target.dataset.tab;
                this.activeTab = tab;
                let tabs = this.tabs;
                tabs.forEach(function (value) {
                    value.active = false;
                });
                item.active = true
            },
            visibilityChanged (isVisible, entry) {
                let menu = this.menu;
                let target = entry.target.dataset.menu;

                if (isVisible) {
                    menu.forEach(function(item){
                        let alias = item.alias
                        if (alias === target) {
                            item.active = true
                        } else {
                            item.active = false
                        }
                    });
                }
            },
            visibilityChanged2 (isVisible, entry) {
                let menu = this.menu2;
                let target = entry.target.dataset.menu;

                if (isVisible) {
                    menu.forEach(function(item){
                        let alias = item.alias
                        if (alias === target) {
                            item.active = true
                        } else {
                            item.active = false
                        }
                    });
                }
            },
            scrollTo() {
                let target = event.target.dataset.item;
                let el = document.querySelector(`[data-menu='${target}']`)
                el.scrollIntoView({block: "center", behavior: "smooth"});
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
            cursor: pointer;
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
            position: sticky;
            top: 20px;

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

            .content {
                h2 {
                    font-size: 32px;
                    line-height: 40px;
                    color: #302E4A;
                    margin: 0 0 10px;
                }
                h3 {
                    font-size: 20px;
                    line-height: 30px;
                    text-transform: uppercase;
                    color: #302E4A;
                    margin: 0 0 10px;
                }
                h4 {
                    font-weight: normal;
                    font-size: 20px;
                    line-height: 27px;
                    color: #302E4A;
                    margin: 0 0 15px;
                }
                p {
                    font-size: 15px;
                    line-height: 24px;
                    letter-spacing: 0.03em;
                    color: rgba(48, 46, 74, 0.8);
                    margin: 0 0 22px;

                    &.lead {
                        font-size: 20px;
                        line-height: 27px;
                        color: #302E4A;
                    }
                }
                ul {
                    padding: 0 0 0 15px;
                    list-style: none;
                    margin: 0 0 48px;

                    li {
                        position: relative;
                        font-size: 15px;
                        line-height: 24px;
                        letter-spacing: 0.03em;
                        color: rgba(48, 46, 74, 0.8);

                        &:not(:last-child) {
                            margin: 0 0 15px;
                        }

                        &::before {
                            content: '';
                            width: 5px;
                            height: 5px;
                            border-radius: 50%;
                            background: #00A7F8;
                            position: absolute;
                            top: 8px;
                            left: -15px;
                        }
                    }
                }
                img {
                    margin: 0 0 25px;
                }
                .advantages {
                    margin: 37px 0 60px;

                    h2 {
                        margin: 0 0 25px;
                    }

                    &-item {
                        padding: 36px 28px 34px 37px;
                        display: grid;
                        grid-template-columns: 68px 1fr;
                        grid-template-rows: auto;
                        grid-column-gap: 28px;
                        grid-row-gap: 0px;
                        background: #FFFFFF;
                        box-shadow: 0px 2px 20px rgba(48, 46, 74, 0.07);
                        border-radius: 5px;

                        h3 {
                            font-size: 20px;
                            line-height: 20px;
                            text-transform: uppercase;
                            color: #302E4A;
                            margin: 0 0 9px;
                        }

                        p {
                            margin: 0;
                            font-size: 15px;
                            line-height: 24px;
                            letter-spacing: 0.03em;
                            color: rgba(48, 46, 74, 0.8);
                        }

                        &:not(:last-child) {
                            margin: 0 0 20px;
                        }
                    }
                }
                .table {
                    margin: 61px 0 62px;
                    width: 100%;
                }
                .characteristics {
                    margin: 0 0 63px;
                    h2 {
                        margin: 0 0 25px;
                    }

                    &-item {
                        position: relative;
                        padding: 31px 37px 24px 53px;
                        background: #FFFFFF;
                        box-shadow: 0px 2px 20px rgba(48, 46, 74, 0.07);
                        border-radius: 5px;

                        h3 {
                            font-size: 20px;
                            line-height: 20px;
                            text-transform: uppercase;
                            color: #302E4A;
                            margin: 0 0 9px;
                        }

                        p {
                            font-size: 15px;
                            line-height: 24px;
                            letter-spacing: 0.03em;
                            color: rgba(48, 46, 74, 0.8);
                            margin: 0;
                        }

                        &::before {
                            content: '';
                            width: 8px;
                            height: 100%;
                            position: absolute;
                            top: 0;
                            left: 0;
                            background: #00A7F8;
                            border-radius: 5px 0 0 5px;
                        }

                        &:not(:last-child) {
                            margin: 0 0 20px;
                        }
                    }
                }
                .charts {
                    margin: 45px 0 35px;
                }
                .chart {
                    margin: 0;
                }
                .price {
                    position: relative;
                    background: #FFFFFF;
                    box-shadow: 0px 2px 20px rgba(48, 46, 74, 0.07);
                    border-radius: 5px;
                    margin: 0 0 20px;

                    h4 {
                        display: inline-block;
                        margin: 25px 37px 11px;
                    }

                    &__list {
                        margin: 0 47px 0 50px;
                        list-style: none;
                        padding: 0;
                        display: grid;
                        grid-template-columns: 1fr auto;
                        grid-column-gap: 58px;
                        grid-row-gap: 0px;

                        &--normal {
                            position: relative;
                            display: block;
                            margin: 0 37px 32px;
                        }
                    }

                    &__total {
                        padding: 10px 10px 11px;
                        display: flex;
                        justify-content: center;
                        align-items: center;
                        border-radius: 0 0 5px 5px;
                        background: #FAFAFA;
                        &-sub {
                            font-weight: bold;
                            font-size: 17px;
                            line-height: 34px;
                            letter-spacing: 0.03em;
                            text-transform: uppercase;
                            color: rgba(48, 46, 74, 0.8);
                            margin: 0 9px 0 0;
                        }
                        &-sum {
                            font-weight: normal;
                            font-size: 21px;
                            line-height: 34px;
                            letter-spacing: 0.03em;
                            color: rgba(48, 46, 74, 0.8);
                        }
                    }
                }
                .result {
                    position: relative;
                    background: #FFFFFF;
                    box-shadow: 0px 2px 20px rgba(48, 46, 74, 0.07);
                    border-radius: 5px;
                    margin: 0 0 62px;
                    padding: 25px 37px 32px;

                    h4 {
                        margin: 0 0 11px;
                    }

                    ul {
                        margin: 0;
                    }
                }
                .product {
                    display: flex;
                    flex-direction: column;
                    &__title {
                        height: 50px;
                        display: flex;
                        justify-content: center;
                        align-items: center;
                        background: #00A7F8;
                        color: #ffffff;
                        font-weight: bold;
                        font-size: 11px;
                        line-height: 16px;
                        text-align: center;
                        text-transform: uppercase;
                    }
                    &__attr {
                        display: flex;
                        justify-content: center;
                        align-items: center;
                        flex-direction: column;
                        height: 50px;

                        &:nth-child(odd) {
                            background: #FAFAFA;
                        }

                        &-title {
                            font-size: 14px;
                            line-height: 16px;
                            text-align: center;
                            letter-spacing: 0.03em;
                            color: rgba(48, 46, 74, 0.8);
                            margin: 0 0 1px;
                        }

                        &-value {
                            font-weight: bold;
                            font-size: 14px;
                            line-height: 16px;
                            text-align: center;
                            letter-spacing: 0.03em;
                            color: rgba(48, 46, 74, 0.8);

                        }
                    }
                }
            }
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
                display: block;
                position: relative;
                &:not(:last-child) {
                    margin: 0 0 45px;
                }
            }
        }
    }
}
</style>
<style lang="scss">
.slider {
    position: relative;
    margin: 25px 0 18px;
    > span {
        position: absolute;
        top: 50%;
        z-index: 999;
        cursor: pointer;
        img {
            display: block;
            margin: 0;
        }
        &:first-child {
            left: -25px;
        }
        &:last-child {
            right: -25px;
        }
    }
}
</style>