# 🧩 Avail Validator Resources

A curated index of validator resources for the Avail  ecosystem, designed to improve discoverability, accessibility, and collaboration across mainnet and testnet participants.

## 🌐 Overview

This repository powers the **Validator Resources** section on the `[Avail Services Page](https://cumulo.pro/services/avail)`, displaying detailed, structured data about validators on both mainnet and testnet. The frontend consumes two JSON files:

- `validators.json`: Mainnet validator resources  


Each entry includes public validator data such as name, moniker, RPC endpoints, APIs, snapshots, explorer links, GitHub repos, and other relevant infrastructure tools.

## ⚙️ How It Works

The data is loaded directly by the services frontend, offering a fast and indexed UI that allows users to search and filter validators and their resources.

All content can be updated via Pull Request, either by contributors or the validators themselves. This makes it easy for any validator to publish or update their own endpoints and tooling with a simple JSON edit.

## 🛠️ Contributing

To propose changes or add your validator’s resources:

1. Fork the repo.
2. Edit the appropriate file (`validators.json`).
3. Submit a Pull Request with a clear description of your changes.

> Make sure your JSON is valid. You can use tools like [JSONLint](https://jsonlint.com) to validate before submitting.

## 📄 JSON Structure Example

```json
 {
    "name": "AKNodes",
    "webservices": "https://services.aknodes.com/other-projetcs/avail-mainnet/sync",
    "x": "AKNodes",
    "validatorlogo": "aknodes.jpg",
    "explorer": "",
    "rpc": "",
    "snapshot": "https://services.aknodes.com/other-projetcs/avail-mainnet/sync",
      "content": {
        "Node Installation": "https://services.aknodes.com/other-projetcs/avail-mainnet/installation"       
    }
 },
   {
    "name": "Cumulo",
    "webservices": "https://cumulo.pro/services/avail/",
    "x": "Cumulo_pro",
    "validatorlogo": "cumulo.jpg",
    "explorer": "https://avail.subscan.io/?rpc=wss://avail.rpc.cumulo.me",
    "rpc": "avail.rpc.cumulo.me",
    "dashboard": "https://explorer.avail.so/?rpc=wss://avail.rpc.cumulo.me"
   }
```
