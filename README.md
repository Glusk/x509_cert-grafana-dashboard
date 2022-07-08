# x509_cert-grafana-dashboard

A Grafana Dashboard for visualizing the data collected by the x509_cert Telegraf plugin for InfluxDB.

The main purpose of this dashboard is to notify you about a certificate expiry but it can also display other certificate errors.
What is more, you can examine certificate chains by filtering your certificates by source.

## Collector Config

Here's a sample `telegraf.conf` file that can be used in combination with this Dashboard:
```toml
[global_tags]
  # Your zone and environment settings, for example
  zone = "europe"
  environment = "production"

[[inputs.x509_cert]]
  # The path to certificates you wish to track
  sources = ['https://foo.bar.com:443']
```

Refer to the [official plugin documentation page](https://github.com/influxdata/telegraf/tree/master/plugins/inputs/x509_cert) for more info:
