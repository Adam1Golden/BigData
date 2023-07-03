# Strimzi Charts

## Strimzi Operator
The operator helm template is the same as the original strimzi, with added egress network policy for the operator namespace. ( define the ports at the values ).

## Kafka Deployments
The kafka charts includes:
<ol>
 <li> kafka cluster ( include the zookeeper cluster) </li>
<li> topics </li>
</ol>
