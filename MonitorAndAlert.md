## Monitoring and Alerting

### Server Monitoring

#### Channels for Server Monitoring

1. **Grafana Monitoring and Notifications**
    - **Description**: Monitor and set notifications for CPU, Memory, and Disk space via Grafana.
    - **Threshold**: Alerts are triggered when usage exceeds 85%.
    - **Notification**: Alerts are sent via Telegram.
    
    ![Grafana CPU Monitoring](images/grafana_cpu.png)

2. **Google Cloud Monitoring and Notifications**
    - **Description**: Monitor and set notifications for CPU, Memory, and Disk space through Google Cloud.
    - **Threshold**: Alerts are triggered when usage exceeds 85%.
    - **Notification**: Alerts are sent via email.
    
    *Setup Alert for CPU*
    ![Google Cloud CPU Setup](images/google_cpu.png)
    
    *Alert*
    ![Google Alert](images/google_alert.png)

3. **Custom Script Monitoring and Notifications**
    - **Description**: Custom script to monitor CPU, Memory, Disk space, and Network usage.
    - **Threshold**: Alerts are triggered when usage exceeds 85%.
    - **Notification**: Alerts are sent via Telegram.
    
    [Script code](https://github.com/suntzu93/system_monitor/blob/main/system_monitor.sh)
    
    *CPU Usage Alert*
    ![Custom Script CPU Alert](images/tool_alert.png)
    
    *Memory Usage Alert*
    ![Custom Script Memory Alert](images/tool_memory.png)
    
    *Disk Usage Alert*
    ![Custom Script Disk Alert](images/tool_disk.png)
    
    *Network Usage Alert*
    ![Custom Script Network Alert](images/tool_network.png)

### Node Health Monitoring

#### Channels for Node Health Monitoring

1. **Custom Script for Block Height Monitoring**
    - **Bridge Node**: 
        - **Description**: Monitor `header.height` of the bridge node every minute.
        - **Condition**: If the height doesn't increase within a minute or the endpoint cannot be requested.
        - **Notification**: Alerts are sent via Telegram.
        
        [Code here](https://github.com/suntzu93/system_monitor/blob/main/bridge_monitor.sh)
        
        ![Bridge Node Alert](images/bridge_node_alert.png)
    
    - **Validator Node**:
        - **Description**: Monitor `latest_block_height` of the validator node every minute.
        - **Condition**: If the height doesn't increase within a minute or the endpoint cannot be requested.
        - **Notification**: Alerts are sent via Telegram.
        
        [Code here](https://github.com/suntzu93/system_monitor/blob/main/validator_monitor.sh)
        
        ![Validator Node Alert](images/validator_alert.png)

2. **Chainnode Tool and Dashboard**
    - **Description**: Utilize Chainnode's tools for network sync status monitoring and alerting.
    - **Thresholds**:
        1. Validator peers < 10 (`cometbft_p2p_peers`)
        2. Validator online < 90% (must always be 100% to ensure quality, metrics: `cometbft_consensus_validators - cometbft_consensus_missing_validators`)
        3. Validator block missing > 20 (`cometbft_consensus_missing_validators`)
        4. Bridge height > 5 (local bridge height is 5 blocks less than the network bridge height, metrics: `bridge_network_height{} - bridge_local_height{}`)
        
        [Code here](https://github.com/suntzu93/CelestiaTools)
    
        ![Bridge and Validator Monitoring](images/bridge_validator_monitor.png)
        
        *Alert Setting*
        ![Bridge and Validator Alert](images/bridge_validator_alert.png)

3. **Grafana Loki for Log Collection**
    - **Description**: Collect logs from multiple servers using Grafana Loki.
    - **Functionality**: View and monitor logs of crucial services. Immediate detection of errors through log analysis.
    
    ![Grafana Loki Log Monitoring 1](images/grafana_loki_log1.png)
    
    ![Grafana Loki Log Monitoring 2](images/grafana_loki_log2.png)
