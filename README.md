# Kibana Streams
Kibana Streams is a tool which routes the counts of logstash events to a metric backend, such as graphite, providing ongoing visibility and enables alerting.

The purpose of this tool is to provide similar capability to graylog's streams.

## Configuration
The configuration is a json file which contains a list of kibana queries, each with its own metric name prefix. The counts of the query results per time interval are sent to graphite. The configuration json file can be a URL, allowing to easily separate the code from the configuration.

Example of a stream definition:
    ```{
        "name" : "errors",
        "description" : "Number of errors in the logs",
        "query" : "@fields.level:'ERROR'",
        "enabled" : "true"
    }```

The tool requires the use of an active kibana2 instance (https://github.com/rashidkpc/Kibana)

## Implementation 
The tool uses a kibana2 instance as an API (instead of just being a UI for interactive queries).

## Thanks
Many thanks to the great Kibana writers! Amazing piece of software

## Contact
Any feedback would be much appreciated, as well as pull requests, of course.

Harel Ben-Attia, harelba@gmail.com, @harelba on Twitter

