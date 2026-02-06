# Fastrax Risk Calculator

Professional day trading risk calculator for position sizing.

## Features

- **Responsive Design**: Works seamlessly on desktop, tablet, and mobile devices
- **Multiple Calculators**: Equity, Options, and Futures (Options and Futures coming soon)
- **Persistent Settings**: Risk values are saved using localStorage
- **Real-time Calculations**: Instant position sizing and risk management

## Equity Calculator

### Mode 1: Calculate Shares & Total Position
- Input: Risk Amount, Entry Price, Stop Price
- Output: Share Count, Total Position Value
- Formula: `Shares = Risk / (Entry - Stop)`, `Position = Entry × Shares`

### Mode 2: Calculate Stop Price
- Input: Risk Amount, Entry Price, Share Count
- Output: Stop Price
- Formula: `Stop = Entry - (Risk / Shares)`

## Deployment

### Local Testing
```bash
docker-compose up -d
```
Access at: http://localhost:8080

### Dokploy Deployment
1. Push to your git repository
2. Create new service in Dokploy
3. Connect to this repository
4. Dokploy will automatically use the Dockerfile
5. Configure domain: risk.fastrax.com
6. Traefik labels are included in docker-compose.yml for automatic routing

### Manual Docker Build
```bash
docker build -t risk-calculator .
docker run -p 8080:80 risk-calculator
```

## Domain

Hosted at: **risk.fastrax.com**

## Example Values

- Risk: $50.00
- Entry: $2.53
- Stop: $2.37
- Shares: 312.50
- Total Position: $790.63