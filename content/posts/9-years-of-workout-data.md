+++ 
draft = true
date = 2024-09-08T09:27:34+08:00
title = "9 years of workout data"
description = ""
slug = "" 
tags = []
categories = []
externalLink = ""
series = []
+++


<script src="https://d3js.org/d3.v7.min.js"></script>

<script src="https://unpkg.com/cal-heatmap/dist/cal-heatmap.min.js"></script>
<script src="https://unpkg.com/cal-heatmap/dist/plugins/CalendarLabel.min.js"></script>
<link rel="stylesheet" href="https://unpkg.com/cal-heatmap/dist/cal-heatmap.css">

<script src="https://unpkg.com/cal-heatmap/dist/plugins/CalendarLabel.min.js"></script>
<script src="https://unpkg.com/cal-heatmap/dist/plugins/LegendLite.min.js"></script>


<script src="https://unpkg.com/@popperjs/core@2"></script>
<script src="https://unpkg.com/cal-heatmap/dist/plugins/Tooltip.min.js"></script>


<div id="cal-heatmap"></div>

<script>


const cal = new CalHeatmap();
cal.paint(
  {
    data: {
        source: [
    {
        "date": "2022-12-14",
        "value": "1"
    },
    {
        "date": "2022-12-15",
        "value": "1"
    },
    {
        "date": "2022-12-17",
        "value": "1"
    },
    {
        "date": "2022-12-20",
        "value": "1"
    },
    {
        "date": "2022-12-23",
        "value": "1"
    },
    {
        "date": "2022-12-26",
        "value": "1"
    },
    {
        "date": "2022-12-26",
        "value": "1"
    },
    {
        "date": "2022-12-29",
        "value": "1"
    },
    {
        "date": "2023-01-02",
        "value": "1"
    },
    {
        "date": "2023-01-04",
        "value": "1"
    },
    {
        "date": "2023-01-13",
        "value": "1"
    },
    {
        "date": "2023-01-16",
        "value": "1"
    },
    {
        "date": "2023-01-19",
        "value": "1"
    },
    {
        "date": "2023-01-26",
        "value": "1"
    },
    {
        "date": "2023-01-28",
        "value": "1"
    },
    {
        "date": "2023-01-30",
        "value": "1"
    },
    {
        "date": "2023-02-01",
        "value": "1"
    },
    {
        "date": "2023-02-04",
        "value": "1"
    },
    {
        "date": "2023-02-13",
        "value": "1"
    },
    {
        "date": "2023-02-15",
        "value": "1"
    },
    {
        "date": "2023-02-20",
        "value": "1"
    },
    {
        "date": "2023-02-22",
        "value": "1"
    },
    {
        "date": "2023-02-24",
        "value": "1"
    },
    {
        "date": "2023-03-09",
        "value": "1"
    },
    {
        "date": "2023-03-11",
        "value": "1"
    },
    {
        "date": "2023-03-15",
        "value": "1"
    },
    {
        "date": "2023-03-16",
        "value": "1"
    },
    {
        "date": "2023-03-17",
        "value": "1"
    },
    {
        "date": "2023-03-21",
        "value": "1"
    },
    {
        "date": "2023-03-25",
        "value": "1"
    },
    {
        "date": "2023-03-27",
        "value": "1"
    },
    {
        "date": "2023-03-29",
        "value": "1"
    },
    {
        "date": "2023-03-31",
        "value": "1"
    },
    {
        "date": "2023-04-03",
        "value": "1"
    },
    {
        "date": "2023-04-07",
        "value": "1"
    },
    {
        "date": "2023-04-10",
        "value": "1"
    },
    {
        "date": "2023-04-12",
        "value": "1"
    },
    {
        "date": "2023-04-16",
        "value": "1"
    },
    {
        "date": "2023-04-20",
        "value": "1"
    },
    {
        "date": "2023-04-21",
        "value": "1"
    },
    {
        "date": "2023-04-25",
        "value": "1"
    },
    {
        "date": "2023-04-27",
        "value": "1"
    },
    {
        "date": "2023-05-01",
        "value": "1"
    },
    {
        "date": "2023-05-11",
        "value": "1"
    },
    {
        "date": "2023-05-12",
        "value": "1"
    },
    {
        "date": "2023-05-13",
        "value": "1"
    },
    {
        "date": "2023-05-26",
        "value": "1"
    },
    {
        "date": "2023-05-27",
        "value": "1"
    },
    {
        "date": "2023-05-29",
        "value": "1"
    },
    {
        "date": "2023-06-01",
        "value": "1"
    },
    {
        "date": "2023-06-02",
        "value": "1"
    },
    {
        "date": "2023-06-03",
        "value": "1"
    },
    {
        "date": "2023-06-05",
        "value": "1"
    },
    {
        "date": "2023-06-08",
        "value": "1"
    },
    {
        "date": "2023-06-09",
        "value": "1"
    },
    {
        "date": "2023-06-11",
        "value": "1"
    },
    {
        "date": "2023-06-12",
        "value": "1"
    },
    {
        "date": "2023-06-14",
        "value": "1"
    },
    {
        "date": "2023-06-17",
        "value": "1"
    },
    {
        "date": "2023-06-18",
        "value": "1"
    },
    {
        "date": "2023-06-20",
        "value": "1"
    },
    {
        "date": "2023-09-16",
        "value": "1"
    },
    {
        "date": "2023-09-18",
        "value": "1"
    },
    {
        "date": "2023-09-20",
        "value": "1"
    },
    {
        "date": "2023-09-22",
        "value": "1"
    },
    {
        "date": "2023-09-25",
        "value": "1"
    },
    {
        "date": "2023-09-27",
        "value": "1"
    },
    {
        "date": "2023-09-29",
        "value": "1"
    },
    {
        "date": "2023-09-30",
        "value": "1"
    },
    {
        "date": "2023-10-02",
        "value": "1"
    },
    {
        "date": "2023-10-05",
        "value": "1"
    },
    {
        "date": "2023-10-09",
        "value": "1"
    },
    {
        "date": "2023-10-11",
        "value": "1"
    },
    {
        "date": "2023-10-14",
        "value": "1"
    },
    {
        "date": "2023-10-17",
        "value": "1"
    },
    {
        "date": "2023-10-19",
        "value": "1"
    },
    {
        "date": "2023-10-21",
        "value": "1"
    },
    {
        "date": "2023-10-23",
        "value": "1"
    },
    {
        "date": "2023-10-26",
        "value": "1"
    },
    {
        "date": "2023-10-27",
        "value": "1"
    },
    {
        "date": "2023-11-06",
        "value": "1"
    },
    {
        "date": "2023-11-08",
        "value": "1"
    },
    {
        "date": "2023-11-10",
        "value": "1"
    },
    {
        "date": "2023-11-13",
        "value": "1"
    },
    {
        "date": "2023-11-15",
        "value": "1"
    },
    {
        "date": "2023-11-17",
        "value": "1"
    },
    {
        "date": "2023-11-20",
        "value": "1"
    },
    {
        "date": "2023-11-22",
        "value": "1"
    },
    {
        "date": "2023-11-24",
        "value": "1"
    },
    {
        "date": "2023-11-28",
        "value": "1"
    },
    {
        "date": "2023-11-29",
        "value": "1"
    },
    {
        "date": "2023-12-02",
        "value": "1"
    },
    {
        "date": "2023-12-04",
        "value": "1"
    },
    {
        "date": "2023-12-06",
        "value": "1"
    },
    {
        "date": "2023-12-08",
        "value": "1"
    },
    {
        "date": "2023-12-11",
        "value": "1"
    },
    {
        "date": "2023-12-18",
        "value": "1"
    },
    {
        "date": "2023-12-19",
        "value": "1"
    },
    {
        "date": "2023-12-20",
        "value": "1"
    },
    {
        "date": "2023-12-22",
        "value": "1"
    },
    {
        "date": "2023-12-26",
        "value": "1"
    },
    {
        "date": "2023-12-27",
        "value": "1"
    },
    {
        "date": "2024-01-07",
        "value": "1"
    },
    {
        "date": "2024-01-10",
        "value": "1"
    },
    {
        "date": "2024-01-12",
        "value": "1"
    },
    {
        "date": "2024-01-14",
        "value": "1"
    },
    {
        "date": "2024-01-16",
        "value": "1"
    },
    {
        "date": "2024-01-18",
        "value": "1"
    },
    {
        "date": "2024-01-19",
        "value": "1"
    },
    {
        "date": "2024-01-22",
        "value": "1"
    },
    {
        "date": "2024-01-23",
        "value": "1"
    },
    {
        "date": "2024-01-24",
        "value": "1"
    },
    {
        "date": "2024-01-26",
        "value": "1"
    },
    {
        "date": "2024-01-29",
        "value": "1"
    },
    {
        "date": "2024-01-29",
        "value": "1"
    },
    {
        "date": "2024-01-31",
        "value": "1"
    },
    {
        "date": "2024-02-02",
        "value": "1"
    },
    {
        "date": "2024-03-26",
        "value": "1"
    },
    {
        "date": "2024-03-30",
        "value": "1"
    },
    {
        "date": "2024-04-01",
        "value": "1"
    },
    {
        "date": "2024-04-03",
        "value": "1"
    },
    {
        "date": "2024-04-04",
        "value": "1"
    },
    {
        "date": "2024-04-06",
        "value": "1"
    },
    {
        "date": "2024-04-09",
        "value": "1"
    },
    {
        "date": "2024-04-11",
        "value": "1"
    },
    {
        "date": "2024-04-13",
        "value": "1"
    },
    {
        "date": "2024-04-15",
        "value": "1"
    },
    {
        "date": "2024-04-16",
        "value": "1"
    },
    {
        "date": "2024-04-19",
        "value": "1"
    },
    {
        "date": "2024-04-22",
        "value": "1"
    },
    {
        "date": "2024-04-25",
        "value": "1"
    },
    {
        "date": "2024-04-27",
        "value": "1"
    },
    {
        "date": "2024-05-01",
        "value": "1"
    },
    {
        "date": "2024-05-03",
        "value": "1"
    },
    {
        "date": "2024-05-05",
        "value": "1"
    },
    {
        "date": "2024-05-09",
        "value": "1"
    },
    {
        "date": "2024-05-10",
        "value": "1"
    },
    {
        "date": "2024-05-13",
        "value": "1"
    },
    {
        "date": "2024-05-16",
        "value": "1"
    },
    {
        "date": "2024-05-17",
        "value": "1"
    },
    {
        "date": "2024-05-22",
        "value": "1"
    },
    {
        "date": "2024-05-24",
        "value": "1"
    },
    {
        "date": "2024-05-28",
        "value": "1"
    },
    {
        "date": "2024-05-30",
        "value": "1"
    },
    {
        "date": "2024-05-31",
        "value": "1"
    },
    {
        "date": "2024-06-03",
        "value": "1"
    },
    {
        "date": "2024-06-07",
        "value": "1"
    },
    {
        "date": "2024-06-09",
        "value": "1"
    },
    {
        "date": "2024-06-11",
        "value": "1"
    },
    {
        "date": "2024-06-13",
        "value": "1"
    },
    {
        "date": "2024-06-15",
        "value": "1"
    },
    {
        "date": "2024-06-17",
        "value": "1"
    },
    {
        "date": "2024-06-23",
        "value": "1"
    },
    {
        "date": "2024-06-24",
        "value": "1"
    },
    {
        "date": "2024-06-26",
        "value": "1"
    },
    {
        "date": "2024-07-09",
        "value": "1"
    },
    {
        "date": "2024-07-10",
        "value": "1"
    },
    {
        "date": "2024-07-11",
        "value": "1"
    },
    {
        "date": "2024-07-20",
        "value": "3"
    },
    {
        "date": "2024-07-31",
        "value": "1"
    },
    {
        "date": "2024-08-01",
        "value": "1"
    },
    {
        "date": "2024-08-02",
        "value": "2"
    },
    {
        "date": "2024-08-09",
        "value": "1"
    },
    {
        "date": "2024-08-10",
        "value": "1"
    },
    {
        "date": "2024-08-14",
        "value": "1"
    },
    {
        "date": "2024-09-03",
        "value": "1"
    },
    {
        "date": "2024-09-06",
        "value": "1"
    }
],
        x: (datum) => +new Date(datum['date']),
        y: (datum) => +datum['value']
    },

    
    date: { locale: {weekStart: 1}, start: new Date('2023-01-01') },
    range: 18,
    scale: {
      color: {
        type: 'threshold',
        range: ['#14432a', '#166b34', '#37a446', '#4dd05a'],
        domain: [1, 2, 3],
      },
    },
    domain: {
      type: 'month',
      gutter: 4,
      label: { text: 'MMM', textAlign: 'start', position: 'top' },
    },
    subDomain: { type: 'ghDay', radius: 2, width: 11, height: 11, gutter: 4 },
    itemSelector: '#cal-heatmap',
  },
  [

[
      Tooltip,
      {
        text: function (date, value, dayjsDate) {
          return (
            (value ? value : 'No') +
            ' workout on ' +
            dayjsDate.format('ddd, MMM D, YYYY')
          );
        },
      },
    ],

    [
      LegendLite,
      {
        includeBlank: true,
        itemSelector: '#ex-ghDay-legend',
        radius: 2,
        width: 11,
        height: 11,
        gutter: 4,
      },
    ],
    [
      CalendarLabel,
      {
        width: 30,
        textAlign: 'start',
        text: () => dayjs.weekdays().map((d, i) => (i % 2 == 0 ? '' : d)),
        padding: [10, 40, 0, 0],
      },
    ],
  ]
);

/*

const cal = new CalHeatmap();
cal.paint({
        itemSelector: "#cal-heatmap",
        data: {
        source: [
            { date: '2024-01-01', value: 3 },
            { date: '2024-01-02', value: 6 },
        ],
        x: (datum) => +new Date(datum['date']),
        y: (datum) => +datum['value']
    },
    date: {
        locale: {weekStart: 1},
        
        min: new Date('2024-01-01'),
        max: new Date('2024-12-31'),
    },

        domain: {
            type: 'month',
            gutter: 4,
            label: {
                text: 'MMM',
                textAlign: 'start',
                position: 'top'
            },
        },

        subDomain: {
            type: 'ghDay',
            radius: 2,
            width: 11,
            height: 11,
            gutter: 4
        },

    },

    [
        [
            CalendarLabel,
            {
                position: 'left',
                key: 'left',
                text: () => ['Mon', '', 'Wed', '', 'Fri', '', 'Sun'],
                textAlign: 'end',
                width: 30,
                padding: [25, 15, 0, 0],
            },
        ],


    ]


);
*/
</script>
