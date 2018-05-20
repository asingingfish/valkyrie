<template>
    <el-container>
        <el-header>
            <h1>租房数据分析</h1>
        </el-header>
        <el-main>
            <el-table :data="rent">
                <el-table-column prop="village" label="小区" width="100"></el-table-column>
                <el-table-column prop="rental" label="租金" width="100"></el-table-column>
                <el-table-column prop="location" label="位置" width="220"></el-table-column>
                <el-table-column prop="feature" label="特点" width="300">
                    <template slot-scope="scope">
                        <el-tag v-for="feature in scope.row.feature" :type="''"
                                disable-transitions>{{feature}}
                        </el-tag>
                    </template>
                </el-table-column>
                <el-table-column prop="bug" label="缺点" width="300">
                    <template slot-scope="scope">
                        <el-tag v-for="bug in scope.row.bug" :type="'info'"
                                disable-transitions>{{bug}}
                        </el-tag>
                    </template>
                </el-table-column>
                <el-table-column prop="rate" label="星级" width="180">
                    <template slot-scope="scope">
                        <el-rate
                            :value="scope.row.rate"
                            disabled
                            show-text
                            text-color="#ff9900"
                            :texts="['极差', '失望', '一般', '满意', '惊喜']">
                        </el-rate>
                    </template>
                </el-table-column>
                <el-table-column prop="link" label="链接" width="80">
                    <template slot-scope="scope">
                        <a :href="scope.row.link" v-if="scope.row.link">查看</a>
                    </template>
                </el-table-column>
            </el-table>
        </el-main>
    </el-container>
</template>

<script>
    import rent from "@/data/rent";

    export default {
        name: "Home",
        componentName: "Home",

        components: {},

        props: {},

        data() {
            return {
                rent
            };
        },

        computed: {},
        watch: {},

        mounted() {
        },
        created() {
        },

        methods: {},


    }
</script>


<style lang="scss">
    $base-gap: 20px;

    .container {
        margin: 0;
        padding: $base-gap;
    }

    .header {
        h1 {
            margin: 0;
        }
    }

    .el-tag {
        margin-right: 10px;
        margin-bottom: 5px;

        &:last-child {
            margin-right: 0;
        }
    }
</style>
