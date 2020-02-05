<template>
  <div id="home">
     <Highcharts :options="areaoptions" />
      <Highcharts :options="columnoption" />
  </div>
</template>

<script>

var areaoption = {
		chart: {
				plotBackgroundColor: null,
				plotBorderWidth: null,
				plotShadow: false,
				type: 'pie'
		},
		title: {
				text: '2018年1月浏览器市场份额'
		},
		tooltip: {
				pointFormat: '{series.name}: <b>{point.percentage:.1f}%</b>'
		},
		plotOptions: {
				pie: {
						allowPointSelect: true,
						cursor: 'pointer',
						dataLabels: {
								enabled: true,
								format: '<b>{point.name}</b>: {point.percentage:.1f} %',
								style: {
									//	color: (Highcharts.theme && Highcharts.theme.contrastTextColor) || 'black'
								}
						}
				}
		},
		series: [{
				name: 'Brands',
				colorByPoint: true,
				data: [{
						name: 'Chrome',
						y: 61.41,
						sliced: true,
						selected: true
				}, {
						name: 'Internet Explorer',
						y: 11.84
				}, {
						name: 'Firefox',
						y: 10.85
				}, {
						name: 'Edge',
						y: 4.67
				}, {
						name: 'Safari',
						y: 4.18
				}, {
						name: 'Sogou Explorer',
						y: 1.64
				}, {
						name: 'Opera',
						y: 1.6
				}, {
						name: 'QQ',
						y: 1.2
				}, {
						name: 'Other',
						y: 2.61
				}]
		}]
};
var  columnoption = {
    chart: {
        type: 'column'
    },
    title: {
        text: '月平均降雨量'
    },
    subtitle: {
        text: '数据来源: WorldClimate.com'
    },
    xAxis: {
        categories: [
            '一月','二月','三月','四月','五月','六月','七月','八月','九月','十月','十一月','十二月'
        ],
        crosshair: true
    },
    yAxis: {
        min: 0,
        title: {
            text: '降雨量 (mm)'
        }
    },
    tooltip: {
        // head + 每个 point + footer 拼接成完整的 table
        headerFormat: '<span style="font-size:10px">{point.key}</span><table>',
        pointFormat: '<tr><td style="color:{series.color};padding:0">{series.name}: </td>' +
        '<td style="padding:0"><b>{point.y:.1f} mm</b></td></tr>',
        footerFormat: '</table>',
        shared: true,
        useHTML: true
    },
    plotOptions: {
        column: {
            borderWidth: 0
        }
    },
    series: [{
        name: '东京',
        data: [49.9, 71.5, 106.4, 129.2, 144.0, 176.0, 135.6, 148.5, 216.4, 194.1, 95.6, 54.4]
    }, {
        name: '纽约',
        data: [83.6, 78.8, 98.5, 93.4, 106.0, 84.5, 105.0, 104.3, 91.2, 83.5, 106.6, 92.3]
    }, {
        name: '伦敦',
        data: [48.9, 38.8, 39.3, 41.4, 47.0, 48.3, 59.0, 59.6, 52.4, 65.2, 59.3, 51.2]
    }, {
        name: '柏林',
        data: [42.4, 33.2, 34.5, 39.7, 52.6, 75.5, 57.4, 60.4, 47.6, 39.1, 46.8, 51.1]
    }]
};
  export default {
    name: 'home',
    data(){
      return {
        areaoptions:areaoption,
        columnoption:columnoption
      }
    },
    methods: {
      open (link) {
        //this.$electron.shell.openExternal(link)
      }
    }
  }
</script>

<style lang="scss">
  
</style>
