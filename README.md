# ⛓️ Blockchain Certificate Management System

A full Ethereum blockchain project for issuing and verifying academic certificates on-chain, built with Solidity smart contracts, Web3.py, and a Python Tkinter GUI — running on a local Ganache blockchain.

---

## ✨ Features

- Certificate Issuance — Admin issues certificates on-chain per student per course
- Batch Certificates — Issue multiple certificates in one transaction
- Certificate Verification — Verify any certificate by querying the blockchain
- User Registration — Register wallet addresses with names on-chain
- Admin Controls — Pause / Resume contract, Transfer ownership
- Token System — Custom ERC-like token with mint and transfer
- Live Alerts — Real-time monitoring of new blocks and transactions
- Activity History — Scan all blockchain blocks for a specific address
- Balance Snapshot — Export all account ETH and token balances to CSV
- History Report — Report showing certificate count per course
- Security Testing — Verifies that non-admin users cannot issue certificates
- Tkinter GUI — Desktop interface for all contract interactions
- Admin Dashboard — Dedicated panel for admin operations

---

## 🗂️ Project Structure

crypto/
├── crypto.py
├── gui.py
├── admin_dashboard.py
├── auto_setup.py
├── live_alert.py
├── activity_history.py
├── history_report.py
├── snapshot_exporter.py
├── security_test.py
└── balances_snapshot.csv

---

## 📜 Smart Contract Functions

### Certificate Contract

| Function | Access | Description |
|----------|--------|-------------|
| registerUser(name) | Public | Register wallet with a name |
| addCertificate(course, student) | Admin only | Issue one certificate |
| batchAddCertificates(courses[], students[]) | Admin only | Issue multiple certificates |
| certificates(id) | Public | Get certificate by ID |
| certCount() | Public | Total certificates issued |
| pause() / resume() | Admin only | Pause or resume contract |
| transferOwnership(newAdmin) | Admin only | Transfer admin role |
| getAdmin() | Public | Get current admin address |

### Token Contract

| Function | Access | Description |
|----------|--------|-------------|
| mint(to, amount) | Admin only | Mint new tokens |
| transfer(to, amount) | Any | Transfer tokens |
| balanceOf(user) | Public | Check token balance |
| totalSupply() | Public | Total tokens in circulation |

---

## 🛠️ Tech Stack

![Solidity](https://img.shields.io/badge/Solidity-Smart_Contract-363636?logo=solidity)
![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python)
![Web3.py](https://img.shields.io/badge/Web3.py-Ethereum-purple)
![Ganache](https://img.shields.io/badge/Ganache-Local_Blockchain-orange)
![Tkinter](https://img.shields.io/badge/GUI-Tkinter-lightblue)

- Solidity — Smart contract language
- Ganache — Local Ethereum blockchain (port 7545)
- Web3.py — Python Ethereum interaction library
- Tkinter — Desktop GUI framework
- CSV — Balance snapshot export

---

## 🚀 How to Run

1. Install Ganache and start it on port 7545
2. Deploy the smart contracts and copy addresses into each file

pip install web3

python gui.py

### Run individual scripts

python live_alert.py          # Monitor live blocks
python activity_history.py    # Scan address history
python snapshot_exporter.py   # Export balances to CSV
python history_report.py      # Report certificates per course
python security_test.py       # Test admin-only access control
python admin_dashboard.py     # Admin operations panel

---

## 📌 Notes

- All certificate data stored permanently on-chain — immutable and tamper-proof
- Only the admin wallet can issue or batch-issue certificates
- Security test confirms non-admin transactions are correctly rejected
- Contract supports pause/resume for emergency scenarios
- Token contract is separate from the certificate contract
