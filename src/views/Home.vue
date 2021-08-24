<template>
    <div class="content">
        <p>홈</p>
        <swiper
            class="swiper"
            :options="swiperOption"
            :space-between="50"
            :style="swiperStyle"
            @swiper="onSwiper"
            @slideChange="onSlideChange"
        >
            <swiper-slide class="card" v-for="item in cards" :key="item">
                <p>
                    <span>{{ item }}</span
                    >&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;
                    <span style="font-size: 12px; color: red; ">위험</span
                    >&emsp;
                    <span style="font-size: 12px; color: blue;">안전</span>
                </p>
                <b-progress
                    :value="value"
                    :max="max"
                    variant="danger"
                    height="5px"
                    :style="{ 'background-color': 'blue', padding: '0px', 'width':'270px'}"
                />
                <p style="font-size: 12px; margin-bottom: 0px;">안전점수</p>
                <p style="font-size: 15px; margin-bottom: 0px; padding-bottom: 0px">{{ max - value }}점</p>
            </swiper-slide>
        </swiper>
        
    </div>
</template>

<script>
import { Swiper, SwiperSlide } from "vue-awesome-swiper";
import "swiper/css/swiper.css";

export default {
    components: {
        Swiper,
        SwiperSlide
    },
    data() {
        return {
            value: 45,
            max: 100,
            swiperOption: {
                slidesPerView: 1,
                spaceBetween: 30,
                centeredSlides: true
            },
            swiperStyle: {},
            cards: ["Today", "Yesterday", "Whole"]
        };
    },
    methods: {
        onSwiper(swiper) {
            console.log(swiper);
        },
        onSlideChange() {
            console.log("slide change");
        }
    }
};
</script>

<style>
@import url(//font.googleapis.com/earlyaccess/notosanskr.css);
.content {
    height: 215.3px;
    border: solid #42bfeb;
    background-color: #42bfeb;
}
.content p {
    text-align: left;
    color: white;
    font-size: 20px;
    font-weight: bold;
    font-family: "@font/noto_sans_cj_kkr";
    padding: 20px 0 0 20px;
}
.content .swiper {
    width: 293px;
    margin: auto;
}
.content .swiper .card {
    padding: 10px 0 0 10px;
    border: solid #ffffff;
    border-radius: 13px;
    background-color: #ffffff;
    height: 107.3px;
    animation: fadein 2s 1s forwards;
    visibility: hidden;
}
@keyframes fadein {
    from {
        opacity: 0;
    }
    to {
        opacity: 1;
        visibility: visible;
    }
}
.content .swiper .card p {
    color: black;
    font-size: 15px;
    font-family: "@font/noto_sans_cj_kkr";
    padding: 0px 0px 0px 5px;
}
</style>
