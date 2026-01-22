[RU](README.ru.md)

<img src="./docs/logo-readme.png" style="max-width:256px;">

# Angelina Trading Platform

**Angelina Trading Platform** is the ecosystem for automating stock trading and analyzing market data, focused on algorithmic, strategy-based trading and reduced human error in decision-making.

The system is built around a high-performance trading core, **Scorpion Engine**, which handles strategy execution, analysis, and risk controls.

---

## Overview

The platform is designed to simplify access to automated trading, to make it user-friendly for a wide audience — from retail users to experienced traders,
while keeping users fully in control of their broker accounts and funds.

Manual trading is often driven by emotions: fear, greed, hesitation, and impulsive decisions.  
Even experienced traders make mistakes when emotions interfere with strategy execution.

Angelina Trading Platform was created to address this problem by providing structured, repeatable, and transparent trading automation based on predefined strategies.

Users connect their existing broker accounts via API keys, select strategies, and enable automated trading — without transferring funds or assets to the platform, or just receive trading signals.

---

## Core Idea

The basic principles of the platform are:

- **Algorithmic strategy-first trading**, without emotions
- **Controlled automation** of the entire trading process, from analysis and search for entry points to trade execution and exit
- **No custody** — funds always remain with the broker
- **Clear separation** between user access and trading logic

Automation is not positioned as a replacement for understanding risk, but as a tool to enforce discipline and consistency.

---

## Platform Structure

### Angelina Trading Platform
The umbrella ecosystem providing access to automated trading functionality and strategy-based workflows.

It consists of two major components:

### Angelina Platform
The service and access layer responsible for:
- user accounts and subscriptions
- strategy selection and configuration
- broker account connection via user-provided API keys
- notifications, reporting, and system feedback
- administrative and operational control

Angelina Platform does **not** execute trades directly.

### Scorpion Engine
A high-performance trading core responsible for:
- strategy execution
- market data processing
- trade orchestration via broker APIs
- risk management logic

Scorpion Engine is designed as a standalone trading engine and may be offered as an independent API-based product in the future.

<img src="./docs/scorpion-logo.png" style="max-width:192px; width:192px;">

---
## User Experience & Onboarding

Key UX principles:
- minimalistic interface without unnecessary noise
- step-by-step onboarding flows
- detailed guides for broker API key setup
- clear explanations at every critical stage

---
## Trading Modes

The platform supports the following interaction options to accommodate different user preferences:

- **Sandbox (Paper Trading)**  
  Strategy evaluation without real trade execution, using simulated orders and realistic performance metrics.

- **Signal-Based Trading**  
  Users receive trading signals and make execution decisions manually.

- **Automated Trading**  
  Strategies can be executed automatically via broker APIs using user-provided credentials.

---

## Trading Instruments

**Currently focused on:**
- Stocks

**Planned support:**
- ETFs
- Derivatives (futures)
- FX instruments

Support for additional instruments is introduced gradually with appropriate risk controls and execution constraints.

---

## Architecture Philosophy

Angelina Trading Platform follows a modular, service-oriented architecture with a strict separation of responsibilities.

User access, configuration, and orchestration are isolated from execution, analysis, and market interaction logic.  
This approach improves scalability, fault isolation, and long-term extensibility.

---

## Project Status

The project is under active development.

- Current stage: **Pre-MVP**
- Initial focus: stock trading automation
- Future direction: strategy marketplace and standalone engine access

---

## Disclaimer

Angelina Trading Platform does not hold user funds, provide brokerage services, or offer investment advice.

All trades are executed via third-party brokers using user-provided API keys.  
Users retain full control over their accounts, strategies, and trading decisions.

---

## Author

**Architecture and development:** Stanislav Kuprienko

Angelina Trading Platform is built as a long-term project focused on algorithmic trading, transparency, and scalable automation.

### ® Angelina ###

<img src="./docs/character.png" style="max-width: 256px; width=256px;">

