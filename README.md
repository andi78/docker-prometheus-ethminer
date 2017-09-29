# Docker Prometheus Ethminer Exporter

Dockerized Prometheus exporter to monitor ethminer log output written in Go.

Exports status up|down and hashrate.

## Known Issues

Does not work if the log file only contains a single line.
This is a side effect of a special check that log lines are ignored when the receding line contains "set work".
The reason is that the hash rate always decreases to around the half of its usual value when these lines occur.
To make monitoring and altering of the hash rates possible its essential that it does not contain the spikes generated by this behaviour.

