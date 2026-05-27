# LAN Setup with Router

## Objective
To design and configure a small Local Area Network (LAN) using a router as the default gateway.

## Topology 
- 1 Router (2911)
- 1 Switch (2960)
- 3 PCs

## IP Addressing
| Device | IP Address       | Subnet Mask     | Gateway       |
|--------|------------------|------------------|---------------|
| PC0    | 192.168.1.10     | 255.255.255.0    | 192.168.1.1   |
| PC1    | 192.168.1.20     | 255.255.255.0    | 192.168.1.1   |
| PC2    | 192.168.1.30     | 255.255.255.0    | 192.168.1.1   |
| Router | 192.168.1.1      | 255.255.255.0    | N/A           |

## Configuration
- Assigned static IP addresses to all PCs
- Configured router interface as default gateway
- Enabled interface using 'no shutdown'

## Testing
- Successfully pinged between all PCs
- Verified connectivity to router

## Troubleshooting
**Issue:** Ping failed due to incorrect default gateway  
**Solution:** Corrected the gateway IP and restored connectivity

## Result
Successfully built and tested a functional LAN with basic troubleshooting.

## Lessons Learned
- Importance of correct gateway configuration
- Basic network troubleshooting approach
