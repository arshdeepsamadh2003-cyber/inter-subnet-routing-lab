# Inter-Subnet Routing Lab

## Project Description

This project demonstrates inter-subnet routing using Containerlab and Docker.

The network contains four hosts, two subnets, two switches, and one router.

## Network Topology

- Subnet A: 192.168.10.0/24
- Subnet B: 192.168.20.0/24
- Router eth1: 192.168.10.1/24
- Router eth2: 192.168.20.1/24

## Host IP Addresses

| Host | IP Address | Default Gateway |
|---|---|---|
| host-a1 | 192.168.10.10/24 | 192.168.10.1 |
| host-a2 | 192.168.10.11/24 | 192.168.10.1 |
| host-b1 | 192.168.20.10/24 | 192.168.20.1 |
| host-b2 | 192.168.20.11/24 | 192.168.20.1 |

## Requirements

- Ubuntu on WSL
- Docker
- Containerlab

## Setup Instructions

1. Open Ubuntu.
2. Go to the project folder.
3. Deploy the topology:

   sudo containerlab deploy -t topology.clab.yml

## Verification

Test communication inside Subnet A:

   sudo docker exec -it clab-inter-subnet-routing-lab-host-a1 ping -c 4 192.168.10.11

Test communication between subnets:

   sudo docker exec -it clab-inter-subnet-routing-lab-host-a1 ping -c 4 192.168.20.10

Test communication inside Subnet B:

   sudo docker exec -it clab-inter-subnet-routing-lab-host-b1 ping -c 4 192.168.20.11

All four network tests passed with 0% packet loss.

## Destroy the Lab

To stop and remove the lab containers:

   sudo containerlab destroy -t topology.clab.yml

## Project Files

- topology.yaml: Required network configuration.
- topology.clab.yml: Containerlab deployment configuration.
- answers.md: Answers to the five lab questions.
- README.md: Project documentation.
