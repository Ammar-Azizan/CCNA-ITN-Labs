# Lab 11.6.6 — Calculate IPv4 Subnets

## Overview

This lab focuses on calculating IPv4 subnet information from a given host IP address, original subnet mask, and new subnet mask.

For each problem, the following information is determined:

- Number of borrowed subnet bits
- Number of subnets created
- Number of remaining host bits
- Number of usable hosts per subnet
- Network address
- First usable host address
- Last usable host address
- Broadcast address

---

## Objectives

- Determine IPv4 subnet information.
- Convert subnet masks to prefix notation.
- Identify borrowed subnet bits.
- Calculate the number of subnets.
- Calculate usable hosts per subnet.
- Determine network and broadcast addresses.
- Determine first and last usable host addresses.

---

# Subnetting Formulas

| Calculation | Formula |
|---|---|
| Subnet bits | `New prefix - Original prefix` |
| Number of subnets | `2^subnet bits` |
| Host bits | `32 - New prefix` |
| Addresses per subnet | `2^host bits` |
| Usable hosts | `2^host bits - 2` |
| First host | `Network address + 1` |
| Last host | `Broadcast address - 1` |

---

# Problem 1

## Given

| Item | Value |
|---|---|
| Host IP | `192.168.200.139` |
| Original mask | `255.255.255.0` (`/24`) |
| New mask | `255.255.255.224` (`/27`) |

## Calculation

```text
Original prefix = /24
New prefix      = /27

Subnet bits = 27 - 24
            = 3

Subnets = 2^3
        = 8

Host bits = 32 - 27
          = 5

Usable hosts = 2^5 - 2
             = 30
```

A `/27` has a block size of:

```text
256 - 224 = 32
```

Subnet ranges:

```text
0
32
64
96
128
160
192
224
```

`192.168.200.139` belongs to:

```text
192.168.200.128 – 192.168.200.159
```

## Result

| Item | Answer |
|---|---|
| Subnet bits | `3` |
| Subnets created | `8` |
| Host bits | `5` |
| Usable hosts per subnet | `30` |
| Network address | `192.168.200.128` |
| First host | `192.168.200.129` |
| Last host | `192.168.200.158` |
| Broadcast address | `192.168.200.159` |

---

# Problem 2

## Given

| Item | Value |
|---|---|
| Host IP | `10.101.99.228` |
| Original mask | `255.0.0.0` (`/8`) |
| New mask | `255.255.128.0` (`/17`) |

## Calculation

```text
Original prefix = /8
New prefix      = /17

Subnet bits = 17 - 8
            = 9

Subnets = 2^9
        = 512

Host bits = 32 - 17
          = 15

Usable hosts = 2^15 - 2
             = 32766
```

A `/17` divides the third octet into:

```text
0 – 127
128 – 255
```

The third octet of the host is `99`, so it belongs to the first range.

## Result

| Item | Answer |
|---|---|
| Subnet bits | `9` |
| Subnets created | `512` |
| Host bits | `15` |
| Usable hosts per subnet | `32766` |
| Network address | `10.101.0.0` |
| First host | `10.101.0.1` |
| Last host | `10.101.127.254` |
| Broadcast address | `10.101.127.255` |

---

# Problem 3

## Given

| Item | Value |
|---|---|
| Host IP | `172.22.32.12` |
| Original mask | `255.255.0.0` (`/16`) |
| New mask | `255.255.224.0` (`/19`) |

## Calculation

```text
Original prefix = /16
New prefix      = /19

Subnet bits = 19 - 16
            = 3

Subnets = 2^3
        = 8

Host bits = 32 - 19
          = 13

Usable hosts = 2^13 - 2
             = 8190
```

Block size:

```text
256 - 224 = 32
```

Third-octet subnet ranges start at:

```text
0, 32, 64, 96, 128, 160, 192, 224
```

The host belongs to:

```text
172.22.32.0 – 172.22.63.255
```

## Result

| Item | Answer |
|---|---|
| Subnet bits | `3` |
| Subnets created | `8` |
| Host bits | `13` |
| Usable hosts per subnet | `8190` |
| Network address | `172.22.32.0` |
| First host | `172.22.32.1` |
| Last host | `172.22.63.254` |
| Broadcast address | `172.22.63.255` |

---

# Problem 4

## Given

| Item | Value |
|---|---|
| Host IP | `192.168.1.245` |
| Original mask | `255.255.255.0` (`/24`) |
| New mask | `255.255.255.252` (`/30`) |

## Calculation

```text
Original prefix = /24
New prefix      = /30

Subnet bits = 30 - 24
            = 6

Subnets = 2^6
        = 64

Host bits = 32 - 30
          = 2

Usable hosts = 2^2 - 2
             = 2
```

Block size:

```text
256 - 252 = 4
```

`245` falls within:

```text
244 – 247
```

## Result

| Item | Answer |
|---|---|
| Subnet bits | `6` |
| Subnets created | `64` |
| Host bits | `2` |
| Usable hosts per subnet | `2` |
| Network address | `192.168.1.244` |
| First host | `192.168.1.245` |
| Last host | `192.168.1.246` |
| Broadcast address | `192.168.1.247` |

---

# Problem 5

## Given

| Item | Value |
|---|---|
| Host IP | `128.107.0.55` |
| Original mask | `255.255.0.0` (`/16`) |
| New mask | `255.255.255.0` (`/24`) |

## Calculation

```text
Original prefix = /16
New prefix      = /24

Subnet bits = 24 - 16
            = 8

Subnets = 2^8
        = 256

Host bits = 32 - 24
          = 8

Usable hosts = 2^8 - 2
             = 254
```

## Result

| Item | Answer |
|---|---|
| Subnet bits | `8` |
| Subnets created | `256` |
| Host bits | `8` |
| Usable hosts per subnet | `254` |
| Network address | `128.107.0.0` |
| First host | `128.107.0.1` |
| Last host | `128.107.0.254` |
| Broadcast address | `128.107.0.255` |

---

# Problem 6

## Given

| Item | Value |
|---|---|
| Host IP | `192.135.250.180` |
| Original mask | `255.255.255.0` (`/24`) |
| New mask | `255.255.255.248` (`/29`) |

## Calculation

```text
Original prefix = /24
New prefix      = /29

Subnet bits = 29 - 24
            = 5

Subnets = 2^5
        = 32

Host bits = 32 - 29
          = 3

Usable hosts = 2^3 - 2
             = 6
```

Block size:

```text
256 - 248 = 8
```

`180` belongs to:

```text
176 – 183
```

## Result

| Item | Answer |
|---|---|
| Subnet bits | `5` |
| Subnets created | `32` |
| Host bits | `3` |
| Usable hosts per subnet | `6` |
| Network address | `192.135.250.176` |
| First host | `192.135.250.177` |
| Last host | `192.135.250.182` |
| Broadcast address | `192.135.250.183` |

---

# Results Summary

| Problem | New Prefix | Subnet Bits | Subnets | Host Bits | Usable Hosts | Network Address | First Host | Last Host | Broadcast |
|---|---:|---:|---:|---:|---:|---|---|---|---|
| 1 | `/27` | `3` | `8` | `5` | `30` | `192.168.200.128` | `192.168.200.129` | `192.168.200.158` | `192.168.200.159` |
| 2 | `/17` | `9` | `512` | `15` | `32766` | `10.101.0.0` | `10.101.0.1` | `10.101.127.254` | `10.101.127.255` |
| 3 | `/19` | `3` | `8` | `13` | `8190` | `172.22.32.0` | `172.22.32.1` | `172.22.63.254` | `172.22.63.255` |
| 4 | `/30` | `6` | `64` | `2` | `2` | `192.168.1.244` | `192.168.1.245` | `192.168.1.246` | `192.168.1.247` |
| 5 | `/24` | `8` | `256` | `8` | `254` | `128.107.0.0` | `128.107.0.1` | `128.107.0.254` | `128.107.0.255` |
| 6 | `/29` | `5` | `32` | `3` | `6` | `192.135.250.176` | `192.135.250.177` | `192.135.250.182` | `192.135.250.183` |

---

# Reflection

### Why is the subnet mask important when analyzing an IPv4 address?

The subnet mask identifies which portion of an IPv4 address represents the network and which portion represents the host.

Without the subnet mask, the network address, broadcast address, valid host range, and subnet size cannot be determined correctly.

---

# Key Findings

- The subnet mask determines the boundary between network and host bits.
- Borrowing host bits creates additional subnets.
- More borrowed bits create more subnets but reduce the number of hosts available in each subnet.
- The network address identifies the subnet.
- The first and last usable addresses can be assigned to hosts.
- The broadcast address represents all hosts on the subnet.
- The block size can be used to quickly identify subnet boundaries.
- CIDR prefix notation provides a concise representation of the subnet mask.

---

# Lab Reference

Cisco Networking Academy — Lab 11.6.6: Calculate IPv4 Subnets