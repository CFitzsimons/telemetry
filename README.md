# Telemetry

## Alloy

- This is a replacement for prometheus, it's still in development but seems handy enough.  You'll need to change the configuration to point to your application under the `metrics_integrations_integrations_nodejs` premetheus scrape in `/alloy/config.alloy`.

## Mimir

- Storage

## Tempo

- APM

## Grafana

- Visualisation

- When connecting Mimir as a datasource, connect using the following URL if using local docker: `http://mimir:9009/prometheus`
- When connecting Tempo as a datasource, connect using the following URL if using local docker: `http://tempo:3200`


## Client

- I use `express-prometheus-middleware` to get additional metrics from the express server as well as the Open Telemetry auto instrumentation library (omitting `fs` events).  The example configuration for auto configuration is in the `insturmentation/sample.*` files.  It's important that these files are loaded _before_ the main application, usually through the `--require ./instrumentation.js` flag.  The express middleware should be configured per the instructions on the npm package.