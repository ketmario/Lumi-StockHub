# Lumi StockHub

![Version](https://img.shields.io/badge/version-1.0.0-blue)
![Framework](https://img.shields.io/badge/Framework-ESX-success)
![Phone](https://img.shields.io/badge/Phone-Quasar%20Smartphone%20V3-orange)

---

# Overview

Lumi StockHub is a premium stock market application developed for **Quasar Smartphone V3** and **ESX Legacy**.

The resource combines **real-world stock market data** with **fully configurable roleplay companies**, allowing players to invest in international corporations as well as custom in-game businesses.

Designed with performance, automation and ease of use in mind, Lumi StockHub automatically manages its database, supports live stock prices via Finnhub and provides an intuitive smartphone interface.

---

# Features

## Real Stock Market

* Live stock prices via Finnhub API
* Automatic market updates
* Configurable market opening hours
* Live daily price changes
* Opening price
* Previous close
* Daily high
* Daily low
* Interactive price history

Supported examples:

* Apple
* Microsoft
* NVIDIA
* Tesla
* Amazon
* Meta
* Google
* JPMorgan
* Visa
* and many more

---

## Roleplay Companies

Create unlimited custom companies.

Examples:

* Benny's Workshop
* Burger Shot
* Bean Machine
* LS Customs
* Dynasty 8
* Taxi Company
* LSPD
* LSFD
* LSMD

Every company can have its own:

* Name
* Symbol
* Category
* Start price
* Volatility
* Market behaviour

---

## Portfolio

Players can

* Buy shares
* Sell shares
* Track average purchase price
* View owned shares
* Track current market value

---

## Market Statistics

Each real stock displays

* Current price
* Daily percentage
* Daily price difference
* Opening price
* Previous closing price
* Daily high
* Daily low

---

## Price History

Each stock automatically stores its market history.

The smartphone displays

* Historical prices
* Interactive chart
* Automatic updates

---

# Automatic Database Management

Lumi StockHub automatically manages its own database.

On startup the resource will:

* Create missing tables
* Create missing indexes
* Create missing columns
* Update existing stock information
* Insert new default stocks
* Preserve player portfolios

No manual SQL updates are required after installation.

---

# Requirements

* ESX Legacy
* oxmysql
* ox_lib
* Quasar Smartphone V3

Optional

* Finnhub API Key (for live stock prices)

---

# Installation

## Step 1

Copy the resource into your server.

```
resources/[quasar]/[smartphone_apps]/lumi_stockhub
```

---

## Step 2

Add the resource to your server.cfg

```
ensure lumi_stockhub
```

---

## Step 3

Configure

```
config/config.lua
```

---

## Step 4

Restart the server.

The resource will automatically create all required database tables.

---

# Configuration

## Debug

```lua
Config.Debug = false
```

Enable or disable console debug output.

---

## Language

```lua
Config.Locale = 'de'
```

Currently supported:

* de
* en

---

## Finnhub

```lua
Config.RealStockApi = 'finnhub'
Config.FinnhubApiKey = ''
```

Create your free API key at

https://finnhub.io

---

## Market Hours

```lua
Config.UseRealMarketHours = true
```

true

Real stocks only update while the real stock market is open.

false

Real stocks update during every market refresh.

Recommended for testing.

---

# Adding Custom Stocks

All default stocks are located inside

```
server/stocks.lua
```

Example

```lua
{
    symbol = "MYSHOP",
    realSymbol = nil,
    name = "My Shop",
    category = "Business",
    startPrice = 120,
    volatility = 2.50
}
```

## Properties

| Property   | Description                           |
| ---------- | ------------------------------------- |
| symbol     | Internal stock symbol                 |
| realSymbol | Finnhub symbol (nil for RP companies) |
| name       | Company name                          |
| category   | Company category                      |
| startPrice | Initial market price                  |
| volatility | Price movement strength               |

---

# Live Stock Market

Real stocks automatically retrieve:

* Current Price
* Percentage Change
* Daily Difference
* Opening Price
* Previous Close
* Daily High
* Daily Low

---

# Commands

## Manual Market Update

```
stockupdate
```

Immediately updates all stock prices.

Useful for testing.

---

# Folder Structure

```
config/
client/
server/
locales/
ui/
```

---

# Performance

The resource is designed to be lightweight.

Features include

* Cached database queries
* Automatic updates
* Minimal client traffic
* Optimized callbacks
* Automatic migration

---

# FAQ

## My real stocks do not update.

Make sure your Finnhub API key is configured correctly.

---

## German stocks return 403.

The free Finnhub plan does not provide every international market.

Use RP companies instead or upgrade your Finnhub plan.

---

## Can I add unlimited companies?

Yes.

Simply add new entries to:

```
server/stocks.lua
```

---

## Do I need to import SQL updates?

No.

The resource updates its own database automatically.

---

# Changelog

## Version 1.0.0

* Initial release
* Real stock market support
* RP company support
* Portfolio system
* Live statistics
* Price history
* Interactive chart
* Automatic database migration
* Modern Quasar Smartphone interface

---

# Support

Luminera Development

GitHub

Discord

---

# License

Copyright © Luminera Development

All rights reserved.
