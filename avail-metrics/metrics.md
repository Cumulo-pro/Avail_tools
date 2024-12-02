# Avail metrics

## Table of Contents

- [Overview](#overview)
  - [Block Height](#block-height)
  - [Build Info](#build-info)
  - [Node Role](#node-role)
  - [Major Syncing](#major-syncing)
  - [Process Start Time](#process-start-time)

- [Node Metrics](#node-metrics)
  - [Average Block Proposal Time](#average-block-proposal-time)
  - [Average Block Construction Time](#average-block-construction-time)
  - [Average Inherent Creation Time](#average-inherent-creation-time)
  - [Block Proposal End Reason](#block-proposal-end-reason)
  - [Number of Transactions](#number-of-transactions)
  - [Number of Transactions in the Queue](#number-of-transactions-in-the-queue)
  - [Number of Blocks in Import Queue](#number-of-blocks-in-import-queue)
  - [Queued Blocks](#queued-blocks)
  - [Number of Known Forks](#number-of-known-forks)
  - [Import Queue Processed Total](#import-queue-processed-total)

- [Node Connectivity](#node-connectivity)
  - [Total Connected Peers](#total-connected-peers)
  - [Active Sync Peers](#active-sync-peers)
  - [Peers Discovered](#peers-discovered)
  - [Incoming Connections Handshake Errors](#incoming-connections-handshake-errors)
  - [Local Addresses Listening](#local-addresses-listening)
  - [Pending Connections](#pending-connections)
  - [Pending Connection Errors](#pending-connection-errors)
  - [Libp2p Distinct Peers Connections (Closed & Opened)](#libp2p-distinct-peers-connections-closed--opened)
  - [Incoming Connections Total](#incoming-connections-total)
  - [Listeners Errors Total](#listeners-errors-total)
  - [Libp2p Connections Closed Total](#libp2p-connections-closed-total)
  - [Libp2p Connections Opened Total](#libp2p-connections-opened-total)
  - [RPC Sessions Closed](#rpc-sessions-closed)
  - [RPC Sessions Opened](#rpc-sessions-opened)
  - [Transaction Propagation Rate](#transaction-propagation-rate)

- [Avail Node Stats](#avail-node-stats)
  - [Task Polling Duration](#task-polling-duration)
  - [Polling Rate Imbalance](#polling-rate-imbalance)
  - [Active Internal Broadcast Channels](#active-internal-broadcast-channels)
  - [Issued Light Client Requests](#issued-light-client-requests)
  - [Queued Blocks in Import Queue](#queued-blocks-in-import-queue)

- [Mempool Stats](#mempool-stats)
  - [Transactions Pruned by Block Events](#transactions-pruned-by-block-events)
  - [Transactions Resubmitted by Block Events](#transactions-resubmitted-by-block-events)
  - [Transactions Submitted](#transactions-submitted)
  - [Transactions Rate Validations Finished](#transactions-rate-validations-finished)
  - [Invalid Transactions Removed](#invalid-transactions-removed)
  - [Transactions Scheduled for Validation](#transactions-scheduled-for-validation)

- [GRANDPA](#grandpa)
  - [GRANDPA's Gossip](#grandpas-gossip)
  - [Grandpa Precommits Total](#grandpa-precommits-total)
  - [Grandpa Prevotes Total](#grandpa-prevotes-total)
  - [Grandpa Finality Round](#grandpa-finality-round)
  - [Total Gossip Expired](#total-gossip-expired)
  - [Finality Grandpa Waiting Messages](#finality-grandpa-waiting-messages)
  - [Justification Import Time](#justification-import-time)

- [Authority Discovery](#authority-discovery)
  - [Failures Handling 'Value Found' Events in DHT](#failures-handling-value-found-events-in-dht)
  - [Known Authorities Count](#known-authorities-count)
  - [Total Times External Addresses Published](#total-times-external-addresses-published)
  - [Pending Authority Address Requests](#pending-authority-address-requests)
  - [DHT Events Received by Authority Discovery](#dht-events-received-by-authority-discovery)
  - [External Addresses Last Published](#external-addresses-last-published)
  - [Total Authority Addresses Requested](#total-authority-addresses-requested)

- [State System](#state-system)
  - [State Cache](#state-cache)
  - [Total Bandwidth Usage](#total-bandwidth-usage)
  - [Evaluation Grid Build Time](#evaluation-grid-build-time)
  - [Average Execution Time](#average-execution-time)
  - [Average Time to Build Commitment](#average-time-to-build-commitment)





![linea transpa](https://github.com/user-attachments/assets/eda24507-f888-406b-ad16-511bd2e23d4c)


## Overview

### Block Height
__substrate_block_height__  

- best: This is the most recent block that the node considers to be the best known block.
- finalised: This is the last block that has been finalised and confirmed as a permanent part of the chain.
- sync_target (sync target): This is the block height target that the node is trying to reach during synchronisation.
  
![image](https://github.com/Cumulo-pro/Avail-tools/assets/2853158/65b3e3b6-7f55-4d5a-8001-38485faeb1ae)

### Build Info   
__substrate_build_info__   

This metric provides static information about the build and network configuration of a Substrate-based node. This metric is useful for identifying the node's software version and network configuration, assisting in debugging and monitoring.  

•	Moniker: Indicates the name of the node or project running.  
•	Node Version: Represents the specific version of the node software in use.  
•	Chain Id: Specifies the blockchain network the node is connected t.o  

![image](https://github.com/user-attachments/assets/7fb1bff4-c773-4259-8b37-f5bf96222c1e)


### Node Role  
__substrate_node_roles__  

Indicates the roles the node is configured to perform within the network. The numeric value corresponds to a specific role or combination of roles the node is performing.  
•  0: None (No roles assigned)  
•  1: Full Node (Participates in block propagation but does not produce blocks)  
•  2: Light Client (Downloads only block headers and necessary state)  
•  4: Authority (Validator or other authority roles)  

![image](https://github.com/user-attachments/assets/ee474572-c930-403e-baf1-e55a7a1cdd43)

### Major Syncing  
__substrate_sub_libp2p_is_major_syncing__

This metric indicates whether the node is performing a major synchronisation or not.   
In a blockchain environment, a major synchronisation can refer to an intensive process where the node catches up with the entire blockchain, downloading and verifying all blocks from the genesis or from a significant fork.  

![image](https://github.com/Cumulo-pro/Avail-tools/assets/2853158/66426365-843d-46ac-ae58-40fec4d9bff9)

### Process Start Time
__time() - substrate_process_start_time_seconds__  

Timestamp indicating when the node process was last started

![image](https://github.com/user-attachments/assets/96d68a76-6251-45af-8293-986abf576395)



![linea transpa](https://github.com/user-attachments/assets/eda24507-f888-406b-ad16-511bd2e23d4c)


## Node metrics

### Average Block Proposal Time
__substrate_proposer_block_proposal_time_sum/substrate_proposer_block_proposal_time_count__  

This metric measures the time it takes to build a block and prepare it for the proposal.  

![image](https://github.com/Cumulo-pro/Avail-tools/assets/2853158/4f125ae2-de9c-474a-b3aa-1ad88b1bdd5b)

### Average Block Construction Time
__substrate_proposer_block_constructed_sum/substrate_proposer_block_constructed_count__  

Time it takes to build blocks in the network. This metric is useful for monitoring the efficiency of the block building process.  

![image](https://github.com/Cumulo-pro/Avail-tools/assets/2853158/180fd64e-7c95-43b5-9cd6-a1a5e967323a)

### Average Inherent Creation Time  
__substrate_proposer_create_inherents_time_sum / substrate_proposer_create_inherents_time_count__  

This metric measures the average time it takes to execute the creation of inherents during block production. Inherents are special extrinsics that are added to blocks without requiring a transaction, such as timestamp updates or session key rotations.

![image](https://github.com/user-attachments/assets/6cd72100-e6a9-413f-adf7-66eaaeb168f1)

### Block Proposal End Reason  
__substrate_proposer_end_proposal_reason__  

This metric tracks the reasons why block proposing was ended. It provides insight into the conditions under which the block production process completes.

![image](https://github.com/user-attachments/assets/c92f4d00-d70c-44fa-a74b-4f6a07b2e32a)


### Num transactions
__substrate_proposer_number_of_transactions__

This metric indicates the number of transactions included in the most recent block in the network.    

![image](https://github.com/Cumulo-pro/Avail-tools/assets/2853158/c64e4980-5dea-4124-9a91-dde91169ee62)


### Number of Transactions in the Queue
__substrate_ready_transactions_number__

This metric indicates the number of transactions that are in the queue of transactions ready to be included in a block.  

![image](https://github.com/Cumulo-pro/Avail-tools/assets/2853158/7c76a4eb-744c-458c-8c5c-f14fc6245c13)

### Num blocks import queue
__substrate_sync_queued_blocks__

Number of blocks that are in the import queue on the chain.  
By observing this metric, node operators can determine if there is a delay in block import and take corrective action if the number of blocks in the queue increases unexpectedly. This metric provides a quick and efficient overview of the block flow within the node, ensuring that the synchronisation process remains smooth and uninterrupted.  

![image](https://github.com/Cumulo-pro/Avail-tools/assets/2853158/47881e72-6d28-42ab-bf90-8b679c1c1144)

### Queued Blocks
__substrate_sync_queued_blocks__

The current number of blocks that are in the import queue to be processed by the network. In the context of a blockchain, block import refers to the process of receiving, validating and adding new blocks to the main chain.
This metric provides crucial information about the congestion or block import workflow on the Avail Turing Network blockchain network, allowing operators and developers to monitor the efficiency and operational status of the network.  

![image](https://github.com/Cumulo-pro/Avail-tools/assets/2853158/578d3ec1-7f7a-46ee-9446-9a313b0f0e6f)

### Number of Known Forks
__substrate_number_leaves__

Measures the number of forks in the chain. An increase in the number of forks may indicate consensus problems or possible attacks on the network. Maintaining a low and stable number of forks is generally a sign of a healthy network.  

### Import Queue Processed Total  
__substrate_import_queue_processed_total__  

This metric is a counter that accumulates the total number of blocks the node has processed through the import queue. A higher value indicates that the node is actively processing blocks. Monitoring this metric can help track the node's performance and activity over time.
Useful for ensuring the import queue is functioning properly and processing blocks without delays or failures. Anomalies, such as a stagnating value, might indicate issues in the queue or synchronization.  

![image](https://github.com/user-attachments/assets/0e934e11-8ff9-400d-8da0-bc2c558327dc)












![linea transpa](https://github.com/user-attachments/assets/eda24507-f888-406b-ad16-511bd2e23d4c)

## Node Connectivity

### Total Connected Peers
__substrate_sub_libp2p_peers_count__ 

Total number of peers connected to the node, regardless of their role. This metric measures all active Libp2p connections, including those not directly participating in synchronization.

![image](https://github.com/Cumulo-pro/Avail-tools/assets/2853158/7a9c1469-237b-48b0-bbd5-098b08966eec)

### Active Sync Peers  
__substrate_sync_peers__  

Number of active peers with which the node is currently synchronizing. This metric specifically measures the peers participating in the block synchronization process.

![image](https://github.com/user-attachments/assets/8b27dd76-33e3-4e04-bd34-a6dd7cd44f51)


### peers Discovered
__substrate_sub_libp2p_peerset_num_discovered__  

Indicates the current number of nodes (or peers) that have been discovered and are stored in the peerset manager.  

![image](https://github.com/Cumulo-pro/Avail-tools/assets/2853158/c012ddc5-580d-4381-8386-530ed1f8b08c)

### Incoming Connections Handshake Errors
__substrate_sub_libp2p_incoming_connections_handshake_errors_total__   

This metric tracks the total number of incoming Libp2p connections that failed during the initial handshake phase. Failures are categorized by their reason.   
•  limit-reached: Connection rejected because the node reached its maximum allowed number of connections.   
•  transport-error: Failure due to a transport-level error.   

This metric helps monitor issues that occur when peers attempt to establish a connection with the node.   
•	High limit-reached Value: Indicates the node is frequently reaching its maximum connection limit. Adjusting limits or scaling resources may be necessary.   
•	High transport-error Value: Suggests potential networking issues, such as peer misconfiguration or unstable network conditions.   

![image](https://github.com/user-attachments/assets/45e39eac-bc9e-4983-af0b-cda95a0f0712)

### Local Addresses Listening  
__substrate_sub_libp2p_listeners_local_addresses__  

This metric tracks the total number of local addresses (network interfaces) where the node is actively listening for incoming Libp2p connections.

![image](https://github.com/user-attachments/assets/e576de9c-f08c-4f5b-b86c-bb9bb4c994a2)

### Pending Connections  
__substrate_sub_libp2p_pending_connections__  

This metric measures the number of pending connections that are in the process of being established on the node using the Libp2p protocol.
Pending connections represent active attempts to establish communication with other nodes. This includes the initial negotiation time, such as the handshake and the configuration of the communication channel.  

![image](https://github.com/user-attachments/assets/83924721-3d55-46c9-aee1-e6e53ec40b37)

### Pending Connection Errors
__substrate_sub_libp2p_pending_connections_errors_total__  

This metric measures the total number of errors that occurred during the establishment of pending connections, categorized by the reason for the error.  
•	invalid-peer-id: Invalid peer ID.  
•	limit-reached: The limit of allowed connections has been reached.  
•	transport-error: Error in the transport layer, such as network failures or disconnections.  

![image](https://github.com/user-attachments/assets/fe1b988c-76b3-4ace-804c-c76c7845d169)

### Libp2p Distinct Peers Connections (Closed & Opened)  

**Connections Closed with Distinct Peers**  
__substrate_sub_libp2p_distinct_peers_connections_closed_total__  

This metric indicates how many distinct peers have disconnected from the node. A high value could result from frequent network rebalancing, churn, or instability.  

**Connections Opened with Distinct Peers**  
__substrate_sub_libp2p_distinct_peers_connections_opened_total__  

This metric shows how many distinct peers the node has successfully connected to. A high value indicates active participation in the network and frequent peer interactions.  

![image](https://github.com/user-attachments/assets/ec92aa1d-f461-4b4d-bad9-75964fdbc870)
 
### Incoming Connections Total  
__rate(substrate_sub_libp2p_incoming_connections_total{job="$job"}[5m])__  

This metric tracks the rate of new connections on the node's listening sockets.  
This metric measures the overall activity of incoming connections, helping to assess the node's exposure and interaction with peers.
High Value: Indicates frequent connection attempts, suggesting active participation in the network.  

![image](https://github.com/user-attachments/assets/cf3504b0-4508-417b-ba63-d219abe98781)

### Listeners Errors Total  
__rate(substrate_sub_libp2p_listeners_errors_total{job="$job"}[5m])__  

This metric tracks the total number of non-fatal errors encountered by Libp2p listeners on the node. Low or Zero Value (0): Indicates stable operation with no non-fatal errors detected.

![image](https://github.com/user-attachments/assets/e7a028d7-ef6d-434c-8ddb-133be770e90f)

### Libp2p Connections Closed Total  
__substrate_sub_libp2p_connections_closed_total__  

This metric tracks the total number of Libp2p connections that have been closed, categorized by direction and reason.  

•  keep-alive-timeout: Connection closed due to inactivity.  
•  ping-timeout: Connection closed because of an unresponsive peer.  
•  protocol-error: Connection closed because of a protocol violation.  
•  sync-notifications-clogged: Notifications queue overflowed.  
•  transport-error: Connection closed due to a transport-level error.  

![image](https://github.com/user-attachments/assets/1c4fa564-e031-4042-aea4-bb653055dfe4)

### Libp2p Connections Opened Total  
__substrate_sub_libp2p_connections_opened_total__  

This metric tracks the total number of Libp2p connections opened by the node, categorized by direction. Direction: Specifies whether the connection was inbound (in) or outbound (out)  

![image](https://github.com/user-attachments/assets/9811eca5-f14c-47d9-8ed5-82c03e17a12e)

### RPC Sessions Closed  
__substrate_rpc_sessions_closed__  

This metric tracks the total number of persistent RPC (Remote Procedure Call) sessions that have been closed by the node. Low Value (0): Indicates that no sessions have been terminated, suggesting a stable connection.  

![image](https://github.com/user-attachments/assets/81f2f677-af95-4c55-8047-98796c071ee3)

### RPC Sessions Opened
__substrate_rpc_sessions_opened__  

This metric tracks the total number of persistent RPC (Remote Procedure Call) sessions opened by the node. 0 indicates that no persistent RPC sessions have been opened.  

![image](https://github.com/user-attachments/assets/6cd7654b-2907-4bfb-9038-f54739af5be5)

### Transaction Propagation Rate  
__rate(substrate_sync_propagated_transactions{chain="avail_turing_network"}[5m])__  

This metric measures the rate of transaction propagation per second from the node to other peers in the blockchain network. It allows to analyze the continuous flow of transactions propagated in 5-minute intervals, providing a dynamic view of the node's efficiency and activity in the network.

![image](https://github.com/user-attachments/assets/9b2632bd-5e53-4fec-a16b-2c3fa1c83b2d)






![linea transpa](https://github.com/user-attachments/assets/eda24507-f888-406b-ad16-511bd2e23d4c)


## Avail Node Stats

### Task Polling Duration 
__substrate_tasks_polling_duration__  

Counts the total number of times the invocation of Future::poll has been started for each specific task. This helps to understand how often tasks are executed compared to the duration of their invocations.  

![image](https://github.com/Cumulo-pro/Avail-tools/assets/2853158/854d9688-6089-4f9b-be28-ea51302256cc)

### Polling Rate Imbalance
__rate(substrate_tasks_polling_started_total[1m]) - rate(substrate_tasks_polling_duration_count[1m])__  

This composite metric is useful for monitoring system performance and efficiency, helping to identify processing problems and optimise the execution of tasks on the network.
Calculates the difference between the start rate and the completion rate of Future::poll invocations.
-A positive value indicates that more poll invocations are being started than are being completed in the last minute.
-A negative value indicates that more poll invocations are being completed than are being started in the last minute.
-A value close to zero suggests that the number of initiated and completed invocations is balanced.  

![image](https://github.com/Cumulo-pro/Avail-tools/assets/2853158/5314f0ad-ba78-4f3b-9a7f-944cc4487236)

### Active Internal Broadcast Channels  
__substrate_sub_libp2p_out_events_num_channels__  

This metric tracks the number of active internal channels that are transmitting network events using the Libp2p protocol.  
Name: Identifies the module associated to the channel.  

![image](https://github.com/user-attachments/assets/7e7eecce-e334-42cf-90a8-f0326fc536bf)

### Issued Light Client Requests 
__substrate_issued_light_requests__  

This metric tracks how many requests the node has sent to light clients for synchronization or data retrieval. A value of 0 means no requests have been made, which may indicate that no light clients are connected or requesting data. An increasing value shows active communication with light clients.  
This metric is useful for monitoring the node's interaction with light clients, especially in networks that prioritize lightweight synchronization and efficiency.  

![image](https://github.com/user-attachments/assets/10c9c9d8-155a-4f37-989c-a5fcee8e7d2f)

###  Queued Blocks in Import Queue  
__substrate_sync_queued_blocks__  

This metric measures the number of blocks currently in the node's import queue. The import queue is where received blocks wait to be processed and validated before being added to the local blockchain.  

![image](https://github.com/user-attachments/assets/a07394d5-f214-4a95-bdf6-1a3174db0ae9)




![linea transpa](https://github.com/user-attachments/assets/eda24507-f888-406b-ad16-511bd2e23d4c)

## mempool stats

### Transactions Pruned by Block Events   
__substrate_sub_txpool_block_transactions_pruned__  

This metric measures the total number of transactions removed from the mempool (transaction pool) due to block-related events.
When a block is finalized or imported, the transactions included in that block are removed from the mempool. This metric tracks how many transactions were removed due to these events.  

![image](https://github.com/user-attachments/assets/a1e03e30-ebce-45b2-b1aa-c50f04421b54)


### Transactions Resubmitted by Block Events  
__substrate_sub_txpool_block_transactions_resubmitted__  

This metric measures the total number of transactions forwarded to the mempool due to block-related events.  
When a block is processed, some transactions in the mempool may not be included in the block for various reasons (e.g., lack of space, low priorities). These transactions may be evaluated and resubmitted for inclusion in future blocks.  

![image](https://github.com/user-attachments/assets/69885d7b-428d-464e-8cb4-9b1f9c5e4d18)

### Transactions Submitted  
__substrate_sub_txpool_submitted_transactions__  

This metric measures the total number of transactions sent to the node's mempool.

![image](https://github.com/user-attachments/assets/5b6e0a59-3de7-42d5-b5dd-ff53955df3f1)

### Transactions Rate Validations Finished  
__rate(substrate_sub_txpool_validations_finished{chain="avail_turing_network"}[5m])__  

This metric measures the rate  total number of transactions that have completed the validation process in the mempool.
Node Activity Indicator: A high volume of validations indicates that the node is actively processing transactions.  

![image](https://github.com/user-attachments/assets/127ecb55-31d9-4cc7-856b-0f8000f77e3f)

###  Invalid Transactions Removed  
__rate(substrate_sub_txpool_validations_invalid{job="$job"}[5m])__  

This metric measures the total number of transactions removed from the mempool because they were considered invalid during the validation process.  
During the validation process, transactions in the mempool are evaluated according to the rules of the blockchain protocol. If a transaction does not comply with these rules, it is marked as invalid and removed from the mempool.  

![image](https://github.com/user-attachments/assets/59b3eda8-16c0-4c41-87da-d078826bc23f)

###  Transactions Scheduled for Validation  
__substrate_sub_txpool_validations_scheduled__  

This metric measures the total number of transactions scheduled for the validation process in the mempool.  
This metric tracks all transactions that have been entered into the mempool and have been scheduled to be validated. A scheduled transaction has not yet been processed, but is in the queue to determine its validity.  

![image](https://github.com/user-attachments/assets/93a619eb-5aa2-4a07-b4f2-0250a89b6d9d)





![linea transpa](https://github.com/user-attachments/assets/eda24507-f888-406b-ad16-511bd2e23d4c)

## GRANDPA

### GRANDPA's gossip
__substrate_finality_grandpa_communication_gossip_validator_messages__  

Information on the number of messages validated by the gossip validator of the GRANDPA (GHOST-based Recursive ANcestor Deriving Prefix Agreement) completion mechanism.  
ES Información sobre el número de mensajes validados por el validador de gossip del mecanismo de finalización GRANDPA (GHOST-based Recursive ANcestor Deriving Prefix Agreement)  

![image](https://github.com/Cumulo-pro/Avail-tools/assets/2853158/0ce80a9d-e021-457d-8e69-68c5b50554cb)

### Grandpa Precommits Total
__substrate_finality_grandpa_precommits_total__  

The metric provides information on the total number of precommits made locally by the GRANDPA (GHOST-based Recursive ANcestor Deriving Prefix Agreement) completion mechanism in the chain.  

![image](https://github.com/Cumulo-pro/Avail-tools/assets/2853158/0f1e478d-e9c7-4879-ae42-61d10d542dae)

### Grandpa Prevotes Total
__substrate_finality_grandpa_prevotes_total__

Information on the total number of prevotes made locally by the GRANDPA (GHOST-based Recursive ANcestor Deriving Prefix Agreement) completion mechanism in the chain.
This metric is useful to monitor the activity and performance of the GRANDPA consensus process in the avail_turing_network chain, providing an indication of the total number of prevotes that have been issued by the validators.  

![image](https://github.com/Cumulo-pro/Avail-tools/assets/2853158/a76df61a-2936-4785-9905-2710fde29af7)

### Grandpa Finality Round
__substrate_finality_grandpa_round__  

Indicates the highest number of completed rounds using the GRANDPA (GHOST-based Recursive ANcestor Deriving Prefix Agreement) completion protocol.
This value can be used to monitor the progress of the network in terms of block completion. An increasing value indicates that the network is progressing and completing more rounds.  

![image](https://github.com/Cumulo-pro/Avail-tools/assets/2853158/7478efaf-5cc0-44dc-a774-d36625abc62b)

### Total Gossip Expired
__substrate_network_gossip_expired_messages_total__  

Total number of messages that have expired and have not been processed by the gossip service.
A high number of expired messages may indicate network overload or problems in message processing, where messages are not handled before they expire.  

![image](https://github.com/Cumulo-pro/Avail-tools/assets/2853158/2a6c7f06-56f3-4c11-bc21-fd57a18b3c7c)

### Finality Grandpa Waiting Messages  
__substrate_finality_grandpa_until_imported_waiting_messages_number__  

Indicates the number of GRANDPA (GHOST-based Recursive ANcestor Deriving Prefix Agreement) finality messages that are waiting in the "until imported" queue. These messages are pending processing before being imported into the node. An increasing value may signal delays or bottlenecks in message processing, which could be due to network congestion or node performance issues. Monitoring this metric helps ensure the efficient processing of finality messages and the smooth operation of the network's consensus protocol.  
This metric is useful for identifying potential issues with message processing efficiency, especially in high-traffic scenarios. Monitoring this value can help ensure that finality processes operate smoothly.  

![image](https://github.com/user-attachments/assets/aacb73c1-d416-4bac-9ead-3ebee5e21d04)

###  Justification Import Time  
__substrate_justification_import_time_bucket__  

Indicates the time taken to import justifications in GRANDPA. This metric is critical for monitoring the performance of the node in processing finality proofs. Lower times indicate that justifications are being processed efficiently, which is essential for maintaining finality performance.  
The metric categorizes the time taken into different buckets (le, or "less than or equal to") for specific thresholds in seconds.  

![image](https://github.com/user-attachments/assets/52cb9468-6a9b-47a7-8932-a0f0b9774b11)




![linea transpa](https://github.com/user-attachments/assets/eda24507-f888-406b-ad16-511bd2e23d4c)


## Authority Discovery

### Failures Handling 'Value Found' Events in DHT  

__substrate_authority_discovery_handle_value_found_event_failure__  

This metric shows the number of times the authority discovery system failed to handle a value_found event in the Distributed Hash Table (DHT). A failure in handling these events means that, although a requested value was found in the DHT, an error occurred during its processing.
Value: 0 – Indicates that no failures have been recorded when handling value_found events so far.

![image](https://github.com/user-attachments/assets/92f76838-56cc-4da2-b755-a9b9204f3a66)

### Known Authorities Count

__substrate_authority_discovery_known_authorities_count__

This metric shows the current number of authority nodes known to the authority discovery system in the network. Known authorities are nodes that have been identified and stored by the system, allowing for reliable connections and communication across the network.  

![image](https://github.com/user-attachments/assets/1e2f6bc1-5276-47fc-b3a1-a4ece127f457)

### Total Times External Addresses Published  

__substrate_authority_discovery_times_published_total__  

This metric shows the total number of times the authority discovery system has published external addresses for the nodes in the network. Each publication event makes the node's external addresses available to other network participants, enhancing connectivity.
If this count is unusually low or stagnant, it might indicate issues with address publication, potentially affecting other nodes' ability to connect.  

![image](https://github.com/user-attachments/assets/0d72abfd-54db-41ea-ba36-53fdbd21ecf9)

### Pending Authority Address Requests  

__substrate_authority_discovery_authority_address_requests_pending__  

This metric shows the number of pending requests for authority addresses in the network. Pending requests represent attempts by nodes to obtain addresses of other authorized nodes (or “authorities”) in the network that have not yet been resolved.
0 – This indicates that there are currently no pending requests for authority addresses in the network.  

![image](https://github.com/user-attachments/assets/f751a087-7be0-4ee3-89e3-5334768d9385)

### DHT Events Received by Authority Discovery  

__substrate_authority_discovery_dht_event_received__  

This metric tracks the number of Distributed Hash Table (DHT) events received by the authority discovery system. Each event type represents different outcomes in DHT operations, such as successfully finding or storing values, which are essential for maintaining network connectivity.  

Values
•	value_found: The number of times a requested value was found in the DHT.  
•	value_not_found: The number of times a requested value was not found in the DHT.  
•	value_put: The number of times a value was successfully stored in the DHT.  
•	value_put_failed: The number of times an attempt to store a value in the DHT failed.  

![image](https://github.com/user-attachments/assets/28a6b88a-88ce-43e0-999d-b62be0e2f69a)

### External Addresses Last Published  

__substrate_authority_discovery_amount_external_addresses_last_published__  

This metric provides the count of external addresses that were published the last time authority discovery updated addresses in the network. It shows the current number of addresses made available by the authority discovery mechanism, which helps other network participants connect and maintain communication with the node.  

![image](https://github.com/user-attachments/assets/50416642-f579-44b4-ac1c-e04ff88decb0)

### Total Authority Addresses Requested  

__substrate_authority_discovery_authority_addresses_requested_total__

This metric shows the total number of times the authority discovery system has requested external addresses of a single authority node within the network. Each request represents an instance where the network attempted to retrieve the address information of a specific authority, which is essential for maintaining node connectivity.
An unexpectedly high or rapidly increasing count could indicate frequent address loss or issues with address retention, prompting more requests than usual. Monitoring this can help identify if connectivity problems are emerging.  

![image](https://github.com/user-attachments/assets/fe65a020-569b-45a9-a6f6-01558b161834)



![linea transpa](https://github.com/user-attachments/assets/eda24507-f888-406b-ad16-511bd2e23d4c)

## State System

### State Cache
__substrate_state_cache_bytes__ 

Indicates the size of the state cache in bytes.  
This metric is useful for monitoring memory resource usage on network nodes. An excessively large cache size may indicate the need to adjust the cache configuration.  

![image](https://github.com/Cumulo-pro/Avail-tools/assets/2853158/a4ea6776-d17b-4c60-b7b4-43d6dfa7fcb6)

### Total Bandwidth Usage 
__substrate_sub_libp2p_network_bytes_total__  

This metric indicates the total bandwidth usage of the libp2p network in bytes. This information is crucial for monitoring, optimising and ensuring network performance.  

![image](https://github.com/Cumulo-pro/Avail-tools/assets/2853158/7a2fb4ef-251a-4541-9e4f-74f56c2d5a16)

### Evaluation Grid Build Time
__avail_header_extension_builder_evaluation_grid_build_time_sum/avail_header_extension_builder_evaluation_grid_build_time_count__  

This metric measures the average time required to build the header extension evaluation grid on an avail_turing_network node.  Building the evaluation grid" refers to the creation of a data structure that organises and evaluates the information in the data block or transactions. This structure can be used for various purposes, including network validation, verification and optimisation.  

![image](https://github.com/Cumulo-pro/Avail-tools/assets/2853158/6ba95d3c-2951-4575-9d75-98872174fe39)

### Average execution time
__avail_header_extension_builder_total_execution_time_sum/avail_header_extension_builder_total_execution_time_count__  

This metric measures the total execution time for the construction of the header extension, the time is reported in microseconds. This metric provides a clear view of the performance of the node in terms of total execution time for the header extension construction.  

![image](https://github.com/Cumulo-pro/Avail-tools/assets/2853158/dbfaa3af-0436-4128-ab0f-34dc3bca65e5)

### Average time to build commitment
__avail_header_extension_builder_commitment_build_time_sum/avail_header_extension_builder_commitment_build_time_count__  

Average time to build the header extension commitment on a node in the avail_turing_network network.
This metric provides a clear view of node performance in terms of building header extension commitment, helping to maintain efficiency and proactively detect potential problems.  

![image](https://github.com/Cumulo-pro/Avail-tools/assets/2853158/3c04efb3-6652-4c2d-8da5-3eda74a9a920)



