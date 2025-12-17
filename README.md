# LumenGauge

Built for Base

LumenGauge is a Base-focused repository intended to provide a clear signal of network availability, wallet connectivity, and RPC correctness across Base environments using official Coinbase tooling.

The project emphasizes repeatable, read-only onchain checks rather than application-specific logic.

## Overview

LumenGauge is designed to:
- Validate Base Mainnet and Base Sepolia connectivity
- Exercise wallet onboarding via OnchainKit
- Perform deterministic RPC reads using Viem
- Expose explicit Basescan references for inspection

## Networks

Base Mainnet  
chainId (decimal): 8453  
Explorer: https://basescan.org  
RPC: https://mainnet.base.org  

Base Sepolia  
chainId (decimal): 84532  
Explorer: https://sepolia.basescan.org  
RPC: https://sepolia.base.org  

## Application Flow

Primary file: app/lumenGauge.ts

When executed, the application:
- Initializes an OnchainKitProvider bound to the selected Base network
- Presents wallet connection UI
- Uses Viem to read:
  - RPC-reported chainId
  - latest block number
  - native ETH balance for a supplied address
- Keeps explorer context visible via Basescan URLs

## Repository Structure

app/  
- lumenGauge.ts  
  React entry component combining wallet UX with Base JSON-RPC reads.

Expected companion files:
- package.json
- tsconfig.json
- index.html / main.tsx
- .env (optional)

## Libraries

OnchainKit  
https://github.com/coinbase/onchainkit  

Viem  
EVM client for Base JSON-RPC reads  

## Installation and Usage

Requirements:
- Node.js 18+
- Browser environment with wallet support

Install dependencies using your preferred package manager and run with a standard React/Vite or Next.js development server.

## License

MIT License

## Author

GitHub: https://github.com/classes-crispy

Public contact (email): classes.crispy0@icloud.com

Public contact (X): https://x.com/raihananwar205

## Testnet Deployment (Base Sepolia)

As part of pre-production validation, one or more contracts may be deployed to the Base Sepolia test network to confirm correct behavior and tooling compatibility.

Network: Base Sepolia  
chainId (decimal): 84532  
Explorer: https://sepolia.basescan.org  

Contract #1 address:  
0x47857d635432705e9fbcb0b80e0c66a9c1572dfb 

Deployment and verification:
- https://sepolia.basescan.org/address/0x47857d635432705e9fbcb0b80e0c66a9c1572dfb
- https://sepolia.basescan.org/0x47857d635432705e9fbcb0b80e0c66a9c1572dfb/0#code  

Contract #2 address:  
0x3c57f2148eb298e88d78f7b909027350ce0fbe59

Deployment and verification:
- https://sepolia.basescan.org/address/0x3c57f2148eb298e88d78f7b909027350ce0fbe59
- https://sepolia.basescan.org/0x3c57f2148eb298e88d78f7b909027350ce0fbe59/0#code  
