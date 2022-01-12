# Trickster  Grafana dashboard
I made this dashboard as tool to benchmark and test [Trickster](https://github.com/Comcast/trickster) 
delta cache for time-series databases. It should speed up loading of your frequently viewed dashboards.

This dashboard should give you good idea about how is Trickster effective in caching, it's utilization 
and chance to observe possible impacts on time-series databases behind it (currently only Prometheus).


## Description
This dashboard uses those metric sources:
- Trickster's own metrics (for most of the important data)
- Prometheus own metrics (for observing impact on Prometheus)
- KubeStateMetrics (those are used only for resources limits display. 
This is Kubernetes specific you can override this by putting static values you use)

Every graph should have description tooltip on the upper left cornet if you hover over it.


## Requirements

### Datasource
- Prometheus datasource _(this can be directly datasource leading to Prometheus 
instance or the Trickster itself if you like recursion :)_

### Variables
To identify Trickster and Prometheus metrics dashboard needs you to specify label, and it's 
value identifying their metrics. Those variables are:
- trickster_label_name - name of the label identifying Trickster metrics (e.g. `app`)
- trickster_label_value - value of the label identifying Trickster metrics (e.g. `trickster`)
- prometheus_label_name - name of the label identifying Prometheus metrics (e.g. `job`)
- prometheus_label_value - value of the label identifying Prometheus metrics (e.g. `prometheus`)

> Values can be regex matchers such as `prometheus.*`


## Installation
There are three ways to install this dashboard

   1. Copy the [`JSON` definition](https://raw.githubusercontent.com/FUSAKLA/trickster-grafana-dashboard/master/dashboard/trickster-dashboard.json)
   of dashboard and paste it in the Import dialog in Grafana
   2. Download the [`JSON` definition](https://raw.githubusercontent.com/FUSAKLA/trickster-grafana-dashboard/master/dashboard/trickster-dashboard.json)
   and using the `Upload .json file` dialog
   3. Load the dashboard directly form [http://Grafana.com](http://Grafana.com) website using
   dashboard ID `5756` or on link [https://grafana.com/dashboards/3681](https://grafana.com/dashboards/5756)


## Screenshots

![Trickster dashboard screenshot](https://grafana.com/api/dashboards/5756/images/3632/image)

## Contributing

Sadly I don't use exact version in production due to some architectonic
reasons and optimizations for my own setup, but it's very much the same.

But I will try to sometimes update this dashboard if I make some major changes.

I'll be happy to add any reasonable feature you would appreciate so don't hesitate to create issue or PR directly. 

Please if you make a PR add also screenshot of your change for easier CR. Thanks!


## Credits

Thanks goes to guys from Comcast who open-sourced the Trickster! 
Great work and thanks :)
