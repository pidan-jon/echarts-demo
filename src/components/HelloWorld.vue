<template>
    <div class="hello">
        <div id="main" style="width: 600px; height: 400px"></div>
    </div>
</template>

<script>
export default {
    name: 'HelloWorld',

    data() {
        return {
            option: {
                title: {
                    text: 'ECharts 入门示例',
                },
                tooltip: {},
                legend: {
                    data: ['销量'],
                },
                xAxis: {
                    data: [
                        '衬衫',
                        '羊毛衫',
                        '雪纺衫',
                        '裤子',
                        '高跟鞋',
                        '袜子',
                    ],
                },
                yAxis: {},
                series: [
                    {
                        name: '销量',
                        type: 'bar',
                        data: [5, 20, 36, 10, 10, 20],
                    },
                ],
            },
        }
    },

    props: {
        msg: String,
    },
    methods: {
        drawChart() {
            // 基于准备好的dom，初始化echarts实例  这个和上面的main对应
            let myChart = this.$echarts.init(document.getElementById('main'))
            // 指定图表的配置项和数据

            // 使用刚指定的配置项和数据显示图表。
            myChart.setOption(this.option)
        },
    },
    mounted() {
        this.drawChart();
    },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
    margin: 40px 0 0;
}
ul {
    list-style-type: none;
    padding: 0;
}
li {
    display: inline-block;
    margin: 0 10px;
}
a {
    color: #42b983;
}
</style>
