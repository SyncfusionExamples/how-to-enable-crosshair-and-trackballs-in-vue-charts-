<template>
  <div id="app">
    <ejs-chart :primaryXAxis="chartPrimaryXAxis" :title="chartTitle"
    :primaryYAxis="chartPrimaryYAxis" :crosshair='chartCrosshair'>
      <e-series-collection>
        <e-series type="Line" :dataSource="chartData" xName="date" yName="sales"></e-series>
      </e-series-collection>   
    </ejs-chart>
  </div>
</template>

<script>
import Vue from "vue";
import { ChartPlugin, DateTime, LineSeries, Crosshair } from '@syncfusion/ej2-vue-charts';
Vue.use(ChartPlugin);

export default {
  provide : {chart : [LineSeries, DateTime, Crosshair]},
  data() {
    return {
      chartCrosshair : {
        enable : true,
        lineType: 'Vertical'
      },
      chartPrimaryYAxis : { 
        title : 'Sales', 
        crosshairTooltip : {
          enable : true,
          fill : "#C1272D",
          textStyle : {
            size :"15px",
            color :"#FFFFFF"
          }
        }
      },
      chartTitle : 'Sales History of the Product',
      chartPrimaryXAxis : {
        valueType : 'DateTime',
        title : 'Years',
        labelFormat: 'yyyy',
        edgeLabelPlacement : 'Shift',
        crosshairTooltip : {
          enable : true,
          fill : "#C1272D",
          textStyle : {
            size :"15px",
            color :"#FFFFFF"
          }
        }
      },
      chartData : [
         { date :  new Date('2011, 01, 01'), sales :80 },
         { date :  new Date('2012, 01, 01'), sales :92 },
         { date :  new Date('2013, 01, 01'), sales :78 },
         { date :  new Date('2014, 01, 01'), sales :85 },
         { date :  new Date('2015, 01, 01'), sales :52 },
         { date :  new Date('2016, 01, 01'), sales :64 },
         { date :  new Date('2017, 01, 01'), sales :87 },
         { date :  new Date('2018, 01, 01'), sales :75 },
         { date :  new Date('2019, 01, 01'), sales :89 },
         { date :  new Date('2020, 01, 01'), sales :83 },
         { date :  new Date('2021, 01, 01'), sales :91 }
      ]
    };
  }
}
</script>


<!-- <template>
  <div id="app">
    <ejs-chart :primaryXAxis="chartPrimaryXAxis" :title="chartTitle"
    :primaryYAxis="chartPrimaryYAxis" :crosshair="chartCrosshair" :tooltip="chartTooltip">
      <e-series-collection>
        <e-series type="Line" :dataSource="chartData" xName="date" yName="sales"
        name="John"></e-series>
        <e-series type="Line" :dataSource="chartData" xName="date" yName="sales1"
        name="Andrew"></e-series>
        <e-series type="Line" :dataSource="chartData" xName="date" yName="sales2"
        name="Thomas"></e-series>
      </e-series-collection>   
    </ejs-chart>
  </div>
</template>

<script>
import Vue from "vue";
import { ChartPlugin, DateTime, LineSeries, Crosshair, Tooltip } from '@syncfusion/ej2-vue-charts';
Vue.use(ChartPlugin);

export default {
  provide : {chart : [LineSeries, DateTime, Crosshair, Tooltip ]},
  data() {
    return {
      chartTooltip : {
        enable : true,
        shared : true,
        format : '${series.name} :  ${point.y}'
      },
      chartCrosshair : {
        enable : true,
        lineType: 'Vertical'
      },
      chartPrimaryYAxis : { 
        title : 'Sales'
      },
      chartTitle : 'Sales History of the Product',
      chartPrimaryXAxis : {
        valueType : 'DateTime',
        edgeLabelPlacement : 'Shift',
        crosshairTooltip : {
          enable : true,
          textStyle : {
            size :"15px",
            color :"#FFFFFF"
          },
          fill : '#C1272D'
        },
        title : 'Years',
        labelFormat: 'yyyy'
      },
      chartData : [
          { date :  new Date('2011, 01, 01'), sales : 80, sales1 : 60, sales2 : 55 },
          { date :  new Date('2012, 01, 01'), sales : 92, sales1 : 70, sales2 : 35 },
          { date :  new Date('2013, 01, 01'), sales : 78, sales1 : 40, sales2 : 25},
          { date :  new Date('2014, 01, 01'), sales : 85, sales1 : 30, sales2 : 15 },
          { date :  new Date('2015, 01, 01'), sales : 52, sales1 : 20, sales2 : 45 },
          { date :  new Date('2016, 01, 01'), sales : 64, sales1 : 50, sales2 : 60 },
          { date :  new Date('2017, 01, 01'), sales : 87, sales1 : 65, sales2 : 83 },
          { date :  new Date('2018, 01, 01'), sales : 75, sales1 : 55, sales2 : 35 },
          { date :  new Date('2019, 01, 01'), sales : 89, sales1 : 65, sales2 : 75 },
          { date :  new Date('2020, 01, 01'), sales : 83, sales1 : 41, sales2 : 65 },
          { date :  new Date('2021, 01, 01'), sales : 91, sales1 : 63, sales2 : 59 }
      ]
    };
  }
}
</script>




 -->
