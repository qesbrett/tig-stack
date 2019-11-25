# TIG stack (Telegraf/InfluxDB/Grafana)
[Telegraf](https://www.influxdata.com/time-series-platform/telegraf/) is a plugin-driven server agent for collecting and reporting metrics.  
[InfluxDB](https://www.influxdata.com/time-series-platform/influxdb/) handle massive amounts of time-stamped information.  
[Grafana](https://grafana.com/) is an open platform for beautiful analytics and monitoring.  

## Requirements
As docker images, TIG stack needs:

* docker v18.* at least
* docker-compose v1.2* at least

To be installed on your machine.

## How to use it?
`.env` to the root directory exposes environment variables:

* **TELEGRAF_HOST** - agent hostname
* **INFLUXDB_HOST** - database hostname
* **INFLUXDB_PORT** - database port
* **INFLUXDB_DATABASE** - database name
* **INFLUXDB_ADMIN_USER** - admin user
* **INFLUXDB_ADMIN_PASSWORD** - admin password
* **GRAFANA_PORT** - monitoring port
* **GRAFANA_USER** - monitoring user
* **GRAFANA_PASSWORD** - monitoring password
* **GRAFANA_PLUGINS_ENABLED** - enable monitoring plugins
* **GRAFANA_PLUGINS** - monitoring plugins list (fetch all available plugins if empty)

Modify it according to your needs and build your custom TIG stack:

```bash
$ docker-compose up -d 
```

### Known issues
* `docker-compose` command fails for non-root user
    1. Create the `docker` group if not exists:

    ```bash
    $ sudo groupadd docker
    ``` 

    2. Add your user to the `docker` group:

    ```bash
    $ usermod -aG docker $USER
    ```

    3. Reboot your machine

Then access graphana at `http://localhost:3000`.

## License
MIT License
Copyright (c) 2019 Q
Copyright (c) 2019 Le Provost

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
