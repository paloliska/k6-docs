---
title: 'CSV'
excerpt: 'You can also make k6 output detailed statistics in a CSV format by using the --out option.'
---

You can also make k6 output detailed statistics in a CSV format by using the `--out/-o` option for `k6 run`, like this:

<CodeGroup labels={["CLI"]}>

```bash
$ k6 run --out csv=my_test_result.csv script.js
```

</CodeGroup>

Or if you want to get the result gzipped, like this:

<CodeGroup labels={["CLI"]}>

```bash
$ k6 run --out csv=my_test_result.gz script.js
```

</CodeGroup>

## CSV format

The CSV result file will contain lines like these:

<CodeGroup labels={["Output"]}>

```plain
metric_name,timestamp,metric_value,check,error,error_code,group,method,name,proto,scenario,status,subproto,tls_version,url,extra_tags
http_reqs,1595325560,1.000000,,,,,GET,http://test.k6.io,HTTP/1.1,default,200,,,http://test.k6.io,
http_req_duration,1595325560,221.899000,,,,,GET,http://test.k6.io,HTTP/1.1,default,200,,,http://test.k6.io,
http_req_blocked,1595325560,225.275000,,,,,GET,http://test.k6.io,HTTP/1.1,default,200,,,http://test.k6.io,
http_req_connecting,1595325560,217.680000,,,,,GET,http://test.k6.io,HTTP/1.1,default,200,,,http://test.k6.io,
http_req_tls_handshaking,1595325560,0.000000,,,,,GET,http://test.k6.io,HTTP/1.1,default,200,,,http://test.k6.io,
http_req_sending,1595325560,0.112000,,,,,GET,http://test.k6.io,HTTP/1.1,default,200,,,http://test.k6.io,
http_req_waiting,1595325560,220.280000,,,,,GET,http://test.k6.io,HTTP/1.1,default,200,,,http://test.k6.io,
http_req_receiving,1595325560,1.507000,,,,,GET,http://test.k6.io,HTTP/1.1,default,200,,,http://test.k6.io,
vus,1595325560,1.000000,,,,,,,,,,,,,
vus_max,1595325560,20.000000,,,,,,,,,,,,,
checks,1595325561,1.000000,status is 200,,,,,,,default,,,,,
checks,1595325561,0.000000,response body,,,,,,,default,,,,,
data_sent,1595325561,76.000000,,,,,,,,default,,,,,
data_received,1595325561,11045.000000,,,,,,,,default,,,,,
iteration_duration,1595325561,1449.049580,,,,,,,,default,,,,,
iterations,1595325561,1.000000,,,,,,,,default,,,,,
```

</CodeGroup>

Each entry in the report represents a metric `metric_name` along with its value `metric_value` at time `timestamp`. If there's an error, then the `error` along with the `error_code` fields will be populated.

## See also

- [Metrics](/using-k6/metrics)
- [Error codes](/javascript-api/error-codes)
