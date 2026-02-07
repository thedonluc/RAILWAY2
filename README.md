# 66mee RAILWAY2 - Epoch Automation

Scheduled service that handles epoch transitions for the 66mee rewards system.

## Setup on Railway

1. Create new project from GitHub repo
2. Set environment variables
3. Set as **Cron Job** trigger: `0 */6 * * *` (every 6 hours)

## What it does

### `node index.js` (start mode — default)
1. Checks if 6-hour epoch is complete
2. Calls `batchStartEpoch()` back-to-back until snapshots finish
3. Starts distribution phase

### `node index.js end`
1. Checks if distribution period is over
2. Calls `batchEndCycle()` to start next accumulation

### `node index.js flush`
1. Calls `flushDistributions()` to pay remaining holders
2. For holders who didn't get paid via buy-triggered distributions

## Environment Variables

```
RPC_URL=https://mainnet.base.org
RAILWAY_PRIVATE_KEY=<your_key>
REWARDS_CONTRACT=<FILL_IN_AFTER_DEPLOY>
```

## Railway Wallet

- Address: `0x0FBFA93c52a083849D933F3e85fbEEEaC6BB2D4f`
- Must be added as allowed executor via `addAllowedExecutor()` (done in deploy script)
