# Strimzi Charts

## Strimzi Operator
The operator helm template is the same as the original strimzi, with added egress network policy for the operator namespace. ( define the ports at the values ).

## Kafka Deployments
The kafka includes:
    1. kafka cluster ( include the zookeeper cluster)
    2. topics