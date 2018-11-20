# echarts-bug-
解决当设置点击事件时，重复调用点击事件的问题
---
// 解决点击事件调用n次的问题
                // 1、清除画布
                myChart.clear()
                // 2、调用setOption
                myChart.setOption(option)
                ///3、在渲染点击事件之前先清除点击事件
                myChart.off('click')
                // triggerEvent为true时，触发点击事件
                myChart.on('click', function (params) {
                    // console.log(params)
                    if (params.value === '订单') {
                        console.log(params.value)
                    }
                })  
