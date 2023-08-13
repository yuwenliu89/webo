<style></style>
<template>
    <div class="bus">
        <h4>
            <img :src="quan.name2.url" alt="">
            <p>{{ this.quan.name2.webos }}</p>
        </h4>
        <div v-for="(item, index) in quan.name2.arr" :key="index" class="c">
            <p>
                <span>{{ index + 1 }}</span>
                <span>{{ item.name }}</span>
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

}
</script>