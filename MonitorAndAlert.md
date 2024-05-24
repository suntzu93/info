
## Monitoring and Alerting

### Server

#### I have 3 channels to monitor the server and notify me of any issues.
`1. I use Grafana to monitor and set notifications for CPU, Memory, and Disk space when they exceed the threshold of 85%. It will notify via Telegram.`

<img src="/images/grafana_cpu.png">


`2. I use Google cloud and set notifications for CPU, Memory, and Disk space when they exceed the threshold of 85%. It will notify via email.`

Setup alert for cpu
<img src="/images/google_cpu.png">

Alert
<img src="/images/google_alert.png">


`3. I'm using my script to monitor CPU, Memory, Disk space, and Network usage when they exceed the threshold of 85%. It will notify via Telegram.`

*[Code here](https://github.com/suntzu93/system_monitor/blob/main/system_monitor.sh)*

*CPU*
<img src="/images/tool_alert.png">

*Memory*
<img src="/images/tool_memory.png">

*Disk*
<img src="/images/tool_disk.png">

*Network*
<img src="/images/tool_network.png">

### Node health

*Bridge node*

`1. I'm using my script to monitor header.height of bridge node every minute. If the height doesn't increase within a minute, it will notify via telegram.`

*[Code here](https://github.com/suntzu93/system_monitor/blob/main/bridge_monitor.sh)*

*Alert* 
<img src="/images/bridge_node_alert.png">

`2. I use the tool and dashboard provided by Chainnode (thanks to them) to monitor and alert.`

*[Code here](https://github.com/suntzu93/CelestiaTools)*

For alerts, I monitor the parameters according to the following thresholds:
1. Validator peers < 10 (cometbft_p2p_peers)
2. Validator online < 90 (it must always be 100 to ensure quality, metric: cometbft_consensus_validators - cometbft_consensus_missing_validators)
3. Validator block missing > 20 (cometbft_consensus_missing_validators)
4. Bridge height > 5 (If the local bridge height is 5 blocks less than the network bridge height, metric: bridge_network_height{} - bridge_local_height{})```


<img src="/images/bridge_validator_monitor.png">

Alert
<img src="/images/bridge_validator_alert.png">
