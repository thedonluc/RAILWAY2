# 77ME RAILWAY2 - Epoch Automation

Runs every 6 hours to handle epoch transitions.

## Setup on Railway

1. Create new project from GitHub repo
2. Set environment variables (copy from .env)
3. Set as "Cron Job" trigger: `0 */6 * * *` (every 6 hours)

## What it does

1. Checks if 6-hour epoch is complete
2. Takes snapshots of holder balances
3. Starts distribution phase
4. Ends cycle when done

## Environment Variables

```
RPC_URL=https://mainnet.base.org
RAILWAY_PRIVATE_KEY=<your_key>
REWARDS_CONTRACT=0x1421c3b0883aefea23482cb88b34b67b4517399a
```

## Railway Wallet

- Address: `0x5aa6c2102a4c6249a5015FB8Aa283765d1259aD1`
- Already set as allowed executor on RewardsContract ✅
