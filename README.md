# ☀️ SolarChain MX

> **Energía solar P2P entre vecinos, potenciado por blockchain.**  
> Vende tu excedente solar. Compra energía limpia más barata que CFE. Todo on-chain, sin intermediarios.

[![Deploy](https://img.shields.io/badge/demo-live-brightgreen)](https://solar-chain-five.vercel.app)
[![Monad](https://img.shields.io/badge/network-Monad%20Testnet-purple)](https://testnet.monadvision.com/address/0x4bf84cfff9B97E1854211F28D26eb8dBF7DA384c)
[![Solidity](https://img.shields.io/badge/solidity-0.8.28-blue)](https://soliditylang.org)
[![License](https://img.shields.io/badge/license-MIT-orange)](LICENSE)

---

## 🌎 El problema

En México, miles de hogares con paneles solares generan excedente de energía que **no pueden vender directamente** a sus vecinos. Al mismo tiempo, esos vecinos pagan tarifas altas a la CFE. SolarChain conecta a ambos usando blockchain como infraestructura de confianza.

---

## ⚡ ¿Cómo funciona?

```
Vecino con paneles          SolarChain MX           Vecino comprador
        │                        │                        │
        │── crearListing() ──▶   │                        │
        │   (publica kWh)        │◀── getListings() ──────│
        │                        │                        │
        │                        │◀── comprarEnergia() ───│
        │                        │    (paga en MON)       │
        │◀── 92% automático ─────│                        │
        │                        │── 8% comisión ──▶ 🏦   │
        │                        │                        │
        │                        │── kWh acreditados ────▶│
```

1. **Vendedor** publica su excedente solar en el marketplace con precio y cantidad en kWh
2. **Comprador** ve las ofertas, cotiza y paga directamente on-chain
3. El **smart contract** distribuye automáticamente: 92% al vendedor, 8% a la plataforma
4. Los kWh quedan acreditados on-chain, integrables con API CFE en v2.0

---

## 🔗 Contrato en vivo

| Red | Dirección |
|-----|-----------|
| Monad Testnet | [`0x4bf84cfff9B97E1854211F28D26eb8dBF7DA384c`](https://monad-testnet.socialscan.io/address/0x4bf84cfff9B97E1854211F28D26eb8dBF7DA384c) |

TX de deploy: [`0x7302666f...`](https://monad-testnet.socialscan.io/tx/0x7302666fade7597d8566f5ffe31a40270b622efe5172fb3db56c86495971564d)

---

## 🛠 Stack tecnológico

| Capa | Tecnología |
|------|-----------|
| Smart Contract | Solidity 0.8.28, EVM Prague |
| Blockchain | Monad Testnet (Chain ID: 10143) |
| Deploy | Foundry (`forge script`) |
| Frontend | HTML + CSS + JavaScript vanilla |
| Web3 | ethers.js v6 |
| Wallet | MetaMask / WalletConnect |
| Hosting | Vercel |

---

## 🚀 Correr localmente

### 1. Clonar el repositorio

```bash
git clone https://github.com/Tania-Sec/Solar-Chain.git
cd Solar-Chain
```

### 2. Abrir el demo

```bash
# Opción simple: abrir directo en el navegador
open solarchain-landing.html

# Opción con servidor local
npx serve .
```

### 3. Configurar la wallet

1. Instala [MetaMask](https://metamask.io)
2. Agrega Monad Testnet:
   - RPC: `https://testnet-rpc.monad.xyz`
   - Chain ID: `10143`
   - Símbolo: `MON`
3. Pide MON gratis en [faucet.monad.xyz](https://faucet.monad.xyz)

---

## 📋 Funciones del Smart Contract

| Función | Quién | Descripción |
|---------|-------|-------------|
| `crearListing(kwh, precio)` | Vendedor | Publica excedente solar |
| `comprarEnergia(id, kwh)` | Comprador | Compra kWh, paga en MON |
| `cotizar(id, kwh)` | Cualquiera | Calcula costo antes de comprar |
| `retirarGanancias()` | Vendedor | Cobra su 92% acumulado |
| `getListingsActivos()` | Cualquiera | Lista todas las ofertas activas |
| `miBalanceKwh()` | Comprador | Ver kWh acreditados |

---

## 💰 Modelo de negocio

```
Por cada transacción:
┌─────────────────────────────┐
│  Comprador paga: 100%       │
│  ├── Vendedor recibe: 92%   │
│  └── Plataforma:      8%   │
└─────────────────────────────┘

Mercado potencial México 2025:
• 1.2M hogares con paneles solares
• ~150 kWh/mes de excedente promedio
• TAM estimado: $180M USD anuales
```

---

## 🗺 Roadmap

- [x] Smart contract desplegado en Monad Testnet
- [x] Frontend con marketplace, simulador y panel vendedor/comprador
- [ ] Integración Privy (wallets sin MetaMask)
- [ ] API CFE para descuento automático en recibo
- [ ] Verificación de paneles solares vía IoT
- [ ] Deploy en Monad Mainnet

---

## 👩‍💻 Autora

**Tania** — [@Tania-Sec](https://github.com/Tania-Sec)

---

## 📄 Licencia

MIT — libre de usar, modificar y distribuir.
