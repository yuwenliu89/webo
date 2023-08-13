<style>
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
</style>
<template>
    <div class="bus">
        <h4>
            <img :src="quan.name.url" alt="">
            <p>{{ this.quan.name.webos }}</p>
        </h4>
        <div v-for="(item, index) in quan.name.arr1" :key="index" class="c">
            <p>
                <span>{{ index + 1 }}</span>
                <span>{{ item.p }}</span>
                <span>{{ item.num }}</span>
            </p>
        </div>
    </div>
</template>
<script>
import mixin from './mixin';
export default {
    mixins: [mixin],
    components: {
        // QuanBu,
    },
    created() {
        return this.quan;
    },
    methods: {
        fun() {
            console.log(this.quan);
        }
    }

}
</script>