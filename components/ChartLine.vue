<template>
    <div class="chart" id="chart"></div>
</template>

<script>

    export default {

        data() {
            return {
                
            }
        },

        mounted() {
            this.chart = this.$c3.generate({
                bindto: '#chart',
                    data: {
                    columns: [
                        ['data1', 30, 200, 100, 400, 150, 250, 20],
                        ['data2', 50, 20, 10, 40, 15, 25, 120]
                    ],
                },
            })
            this.addData()
        },

        methods: {
            addData() {
                setTimeout(() => {
                    this.chart.load({
                        columns: [
                            ['data3', 300, 100, 250, 150, 300, 150, 500],
                            ['data4', 100, 200, 150, 50, 100, 250, 40]
                        ]
                    });
                }, 2000)
            }
        }
    }
</script>

<style lang="css" scoped>

</style>