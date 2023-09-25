[[Route 53]] has a few routing policies that can be used.

## Simple
A simple name to address mapping

## Failover
A backup. If the main entry fails, this is used instead

## Geolocation
Based on customer location, it will route the traffic. For example, if you’re in Europe, it routes to Europe

## Geoproximity
Based on customer location to an *AWS Region*. For example, if you are closer to us-east-1 it will route you there

## Latency
Routes customer to the lowest latency address

## Multivalue Answer
Kind of like a load balancer. Provides a number of IP addresses as the answer to balance spread

## Weighted
Allows weights to be assigned on which address to provide.