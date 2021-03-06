# KAFKA INTEGRATION LABS
<br>

# 1. About

This set of HoLs features Kafka integration with ADX and covers "how to integrate" with both the popluar Kafka offerings we see on Azure - **HDInsight Kafka**,  **Confluent Kafka IaaS** and **Confluent Cloud Kafka PaaS**.  <br>

## 1.1. HDInsight Kafka
Is Azure's managed Kafka as a service with disaggregated compute and storage model and unlike other offerings of HDInsight, actually leverages managed disks with an option for you to choose a SKU with SSD/premium disks and also configure number of disks per node.<br><br>

## 1.2. Confluent IaaS Kafka - Operator based on Azure Kubernetes Service
Featured in this labs is a licensed (free for 30 days) version of Kafka from Confluent, runs on Azure Kubernetes Service (AKS), and leverages the Confluent operator for provisioning on AKS.<br><br>  

## 1.3. Confluent PaaS Kafka - Confluent Cloud
Featured in this [lab](https://github.com/Azure/azure-kusto-labs/blob/master/kafka-integration/confluent-cloud/README.md) is cloud, managed, PaaS offering of Kafka from Confluent.<br><br> 

## 1.4. About the labs
The labs are:
- **end to end** 
- **scripted** (no need to bing/google - not a hack) and **self contained**
- they include **provisioning** the Kafka and KafkaConnect environments (and ADX, and Azure Databricks Spark to serve as producer) and starting services
- **downloading and curating data** for the lab (Spark)
- **producing/publishing** to Kafka (Spark)
- **integrating** into ADX (KafkaConnect)
- both **standalone** and **distributed** modes are covered, with distributed mode featuring Kusto connectors running on containers hosted on Azure Kubernetes Service.
- they come with detailed instructions, and include all commands for the lab
- the labs that feature distributed modes of KafkaConnect also feature secure environments (**VNet injected** Kafka, Azure Databricks and Azure Data Explorer)
- Dedicate at least 4-8 hours for each of the labs that features KafkaConnect in distrbuted mode

# 2. Standalone KafkaConnect on Docker separately, and with HDInsight Kafka 3.6 separately

| # | Focus | Level |Time to complete |
| :--- | :--- | :--- | :--- |
| 1 | [Standalone KafkaConnect on Docker](dockerized-quickstart/README.md) | 200 | 1-2 hours|
| 2 | [Standalone KafkaConnect with HDInsight Kafka](standalone-mode/README.md) | 300 | 4-8 hours|

This lab environment can be deleted.  The distributed KafkaConnect labs do not use this environment.

# 3. Distributed KafkaConnect with HDInsight Kafka and Confluent Kafka IaaS, separately

This set of labs features HDInsight Kafka 3.6 with associated KafkaConnect workers running on Azure Kubernetes service and Confluent Kafka and associated KafkaConnect workers running on the same Azure Kubernetes service cluster.  Azure Databricks is leveraged to download public dataset, curate it and publish to Kafka for the lab.  All services are Vnet injected as mentioned earlier.  The documentation for this lab is shared across both Kafka offerings so you can complete them back to back in the order you choose.  Its a level 400 lab in terms of overall complexity (due to provisioning and configuration).  Allocate about 8 hours for the first lab and about 6-7 hours for the second as it builds on the same environment.<br>

| # | Focus | Level |Time to complete |
| :--- | :--- | :--- | :--- | 
| 1 | [Common environment provisioning](distributed-mode/common/README.md) | 300 | 2 hours |
| 2 | [Distributed KafkaConnect Kusto integration with Confluent Kafka](distributed-mode/confluent-kafka/README.md) | 300 | 8-16 hours|
| 3 | [HDInsight Kafka based distributed KafkaConnect Kusto integration](distributed-mode/hdinsight-kafka/README.md) | 300 | 8 hours|

# 4. Distributed KafkaConnect with Confluent Cloud (Kafka PaaS managed by Confluent)

**This [lab](https://github.com/Azure/azure-kusto-labs/blob/master/kafka-integration/confluent-cloud/README.md) is independent of the above labs**, does not use the common environment, and features Confluent Cloud, with connectors running on Azure Kubernetes Service.  Azure Databricks is leveraged to download a public dataset, curate it and publish to Kafka for the lab.  The documentation and resources for this lab have no dependency on the labs above.  Allocate about 8-10 hours for this lab.<br>
