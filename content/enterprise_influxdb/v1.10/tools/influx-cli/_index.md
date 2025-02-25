---
title: influx - InfluxDB command line interface
menu:
  enterprise_influxdb_1_10:
    name: influx
    weight: 10
    parent: Tools
v2: /influxdb/v2.0/reference/cli/influx/
---

The `influx` command line interface (CLI) includes commands to manage many aspects of InfluxDB, including databases, organizations, users, and tasks.


## Usage

```
influx [flags]
```


## Flags {.no-shorthand}

| Flag              | Description                                                                                           |
|-------------------|-------------------------------------------------------------------------------------------------------|
| `-version`        | Display the version and exit                                                                          |
| `-url-prefix`     | Path to add to the URL after the host and port. Specifies a custom endpoint to connect to.            |
| `-host`           | HTTP address of InfluxDB (default: `http://localhost:8086`)                                           |
| `-port`           | Port to connect to                                                                                    |
| `-socket`         | Unix socket to connect to                                                                             |
| `-database`       | Database to connect to the server                                                                     |
| `-password`       | Password to connect to the server. Leaving blank will prompt for password (`--password ''`).          |
| `-username`       | Username to connect to the server                                                                     |
| `-ssl`            | Use https for requests                                                                                |
| `-unsafessl`      | Set this when connecting to the cluster using https                                                   |
| `-execute`        | Execute command and quit                                                                              |
| `-format`         | Specify the format of the server responses: json, csv, or column                                      |
| `-precision`      | Specify the format of the timestamp: rfc3339, h, m, s, ms, u or ns                                    |
| `-consistency`    | Set write consistency level: any, one, quorum, or all                                                 |
| `-pretty`         | Turns on pretty print for JSON format                                                                 |
| `-import`         | Import a previous database export from file                                                           |
| `-pps`            | Points per second the import will allow. The default is `0` and will not throttle importing.          |
| `-path`           | Path to file to import                                                                                |
| `-compressed`     | Set to true if the import file is compressed                                                          |

{{< children >}}
