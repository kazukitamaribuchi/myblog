<template>
    <div id="header_area_wrap">
        <FixedFadeInHeader/>
        <v-card
            flat
            tile
            class="header_wrap"
        >
            <div id="header_top">
                <v-row>
                    <v-col cols="3" class="header_top_left">
                        <!-- <GridBtn/> -->
                    </v-col>
                    <v-col cols="6" class="header_top_title">
                        <v-card-title>krystasis</v-card-title>
                    </v-col>
                    <v-col cols="3" class="header_top_right">
                        <SearchArea/>
                        <!-- <vs-input
                            class="header_top_search"
                            v-model="searchText"
                            placeholder="search..."
                        >
                            <template #icon>
                                <i class='bx bx-search'></i>
                            </template>
                        </vs-input> -->
                    </v-col>
                </v-row>
            </div>
            <div id="header_middle">
                <v-row>
                    <v-spacer/>
                    <v-col
                        cols="2"
                        class="sns_icon_area_wrap"
                    >
                        <SnsIcons/>
                    </v-col>
                </v-row>
            </div>
        </v-card>
        <div id="header_bottom_wrap">
            <HeaderBottom/>
        </div>
    </div>
</template>
<script>
    import FixedFadeInHeader from '@/components/common/FixedFadeInHeader'
    import HeaderBottom from '@/components/parts/HeaderBottom'
    import SnsIcons from '@/components/common/SnsIcons'
    import GridBtn from '@/components/parts/GridBtn'
    import SearchArea from '@/components/parts/SearchArea'
    import { mapGetters } from 'vuex'

    export default {
        name: 'Header',
        components: {
            HeaderBottom,
            GridBtn,
            SnsIcons,
            FixedFadeInHeader,
            SearchArea
        },
        props: {
        },
        data: () => ({
            searchText: '',
            fixedSearchText: '',
            scrollY: 0,
        }),
        beforeCreate () {
        },
        created () {
        },
        beforeMount () {
        },
        mounted () {
        },
        beforeUpdate () {
        },
        update () {
        },
        beforeDestroy () {
        },
        destoryd () {
        },
        watch: {
        },
        computed: {
            ...mapGetters([
                'activeFixed',
            ])
        },
        methods: {
        },
        mixins: [],
    }
</script>
<style lang="scss" scoped>
    @keyframes fadeIn {
        0% {
            opacity: 0;
        }
        50% {
            opacity: 0.4;
        }
        100% {
            opacity: 1;
        }
    }
    @keyframes fadeOut {
        0% {
            opacity: 1;
        }
        50% {
            opacity: 0.6;
        }
        100% {
            opacity: 0;
        }
    }
    @keyframes slideTopIn {
        0% {
            opacity: 0;
            transform: translateY(-30px);
        }
        50% {
            opacity: 0.4;
            transform: translateY(-10px);
        }
        100% {
            opacity: 1;
            transform: translateY(0);
        }
    }
    @keyframes slideLeftIn {
        0% {
            opacity: 0;
            transform: translateX(-30px);
        }
        50% {
            opacity: 0.4;
            transform: translateX(-10px);
        }
        100% {
            opacity: 1;
            transform: translateX(0);
        }
    }
    @keyframes slideRightIn {
        0% {
            opacity: 0;
            transform: translateX(30px);
        }
        50% {
            opacity: 0.4;
            transform: translateX(10px);
        }
        100% {
            opacity: 1;
            transform: translateX(0);
        }
    }
    @keyframes fontUpBlogTitle {
        0% {
            opacity: 0;
            font-size: 30px;
        }
        50% {
            opacity: 0.4;
            font-size: 35px;
        }
        100% {
            opacity: 1;
            font-size: 40px;
        }
    }
    #header_area_wrap {
        .fixed_header_area_wrap {
            padding-top: 10px;
            .fixed_header_area {
                max-width: 100%;
                .fixed_header_icon {
                    cursor: pointer;
                    font-family: 'Kaushan Script', cursive;
                    font-size: 22px;
                    opacity: 0;
                    animation: slideLeftIn 0.3s ease-out 0.2s 1 normal forwards running;
                    // padding-left: 150px;
                }
                .fixed_header_grid {
                    position: relative;
                    top: -5px;
                    left: 10px;
                    opacity: 0;
                    animation: slideLeftIn 0.3s ease-out 0.2s 1 normal forwards running;
                }
                .fixed_header_menu_area {
                    opacity: 0;
                    animation: slideTopIn 0.3s ease-out 0.2s 1 normal forwards running;
                }
                .fixed_header_search_btn {
                    opacity: 0;
                    position: relative;
                    top: 4px;
                    left: 5px;
                    text-align: center;
                    display: block;
                    cursor: pointer;
                    animation: slideRightIn 0.3s ease-out 0.2s 1 normal forwards running;
                }
            }
        }
        .noDisplay {
            display: none !important;
        }
        .activeFixed {
            // opacity: 0;
            // animation: fadeIn 0.3s ease-out 0.4s 1 normal forwards running;
            z-index: 10000;
            display: block;
            position: fixed;
            top: 0;
            left: 0;
            height: auto;
            width: 100%;
            background-color: rgba(255, 255, 255, 0.9);
            // background-color: rgba(50, 50, 50, 0.9);
            // color: white;
        }
        width: 100%;
        height: 250px;
        .header_wrap {
            width: 1200px;
            margin: 0 auto;
            #header_top {
                width: 100%;
                height: 180px;
                .v-card__title::v-deep {
                    display: block;
                    text-align: center;
                    // font-size: 40px;
                    opacity: 0;
                    animation: fontUpBlogTitle 0.3s ease-out 0.4s 1 normal forwards running;
                }
                padding-top: 20px;
                .header_top_title {
                    font-family: 'Kaushan Script', cursive;
                    padding-top: 45px;
                }
                .header_top_left {
                }
                .header_top_right {
                    .header_top_search {
                        float: right;
                    }
                }
            }
            #header_middle {
                width: 100%;
                height: 40px;
                .sns_icon_area_wrap {
                    padding-left: 50px;
                }
            }
            .vs-input-content {
                margin: 0 auto;
            }
        }
        #header_bottom_wrap {
            opacity: 0;
            animation: fadeIn 0.3s ease-out 0.2s 1 normal forwards running;
            width: 1200px;
            text-align: center;
            height: 30px;
            margin: 0 auto;
        }
    }
</style>
