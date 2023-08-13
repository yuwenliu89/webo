<style>
.a {
    width: 100%;
    height: 400px;
    float: left;
}

.b {
    width: 260px;
    height: 28px;
    border-radius: 9px;
    margin-top: 5px;
    margin-bottom: 5px;
}

.quans {
    width: 280px;
    height: 400px;
    float: left;
}

.quans div {
    width: 180px;
    height: 40px;
}

.quans img {
    width: 25px;
    height: 25px;
    float: left;
    margin-top: 7.5px;
}

.quans p {
    width: 90px;
    height: 40px;
    line-height: 40px;

}

.bus {
    width: 1029px;
    height: 400px;
    float: right;
}

.bus h4 {
    width: 100%;
    height: 60px;

}

.bus h4 img {
    width: 40px;
    height: 40px;
    float: left;
    margin-top: 10px;
}

.bus h4 p {
    width: 400px;
    height: 40px;
    margin-top: 10px;
    float: left;
    text-align: left;
    line-height: 40px;
    text-indent: 1em;
}

.c {
    width: 100%;
    height: 31px;
    line-height: 31px;
    float: left;
}

.c p:hover {
    color: rgba(24, 144, 255);
}

.c p span:nth-child(1) {
    float: left;
}

.c p span:nth-child(2) {
    text-indent: 1em;
    float: left;
}

.c p span:nth-child(3) {
    float: right;
    margin-right: 5px;
}

.ans {
    background-color: rgba(24, 144, 255);
    color: white;
}
</style>
<template>
    <div class="a">
        <div class="quans">
            <input type="text" class="b" placeholder="搜索">
            <div v-for="(item, index) in quan.name.arr" :key="index" :class="{ 'ans': selectedIndex === index }"
                v-on:click="bei(dian[selectedIndex], index)">
                <img :src="item.url" alt="">
                <p>{{ item.name }}</p>
            </div>
        </div>
        <div>
            <component :is="currentComponent"></component>
        </div>

    </div>
</template>
<script>
import ZhiHu from './ZhiHu.vue';
import WeiXin from './WeiXin.vue';
import BaiDu from './BaiDu.vue';
import SanLiu from './SanLiu.vue';
import ShaoShu from './ShaoShu.vue';
import HuWang from './HuWang.vue';
import WeBoBox from './WeBoBox.vue';
import IT from './IT.vue';

import mixin from './mixin';
export default {
    mixins: [mixin],
    data() {
        return {
            selectedIndex: 0,
            currentComponent: 'WeBoBox',
            dian: ["WeBoBox", "ZhiHu", "WeiXin", "BaiDu", "SanLiu", "ShaoShu", "HuWang", "IT"]
        };
    },
    components: {
        ZhiHu,
        WeiXin,
        IT,
        HuWang,
        ShaoShu,
        SanLiu,
        BaiDu,
        WeBoBox,
    },
    created() {
        return this.quan;
    },
    watch: {


    },
    methods: {
        bei(component, index) {
            if (this.selectedIndex !== -1) {
                this.quan.name.arr[this.selectedIndex].zt = false;

            }
            this.selectedIndex = index;
            this.quan.name.arr[this.selectedIndex].zt = true;
            if (this.selectedIndex === index) {
                this.currentComponent = component;
            }

        },
    },
}
</script>