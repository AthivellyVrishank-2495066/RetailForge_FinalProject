# RetailForge Inventory Management System

## Project Overview

RetailForge is a modular C++98 inventory management system built for retail businesses. It combines product and supplier management, sales transaction tracking, forecasting, reporting, and backup/restore support using standard STL containers.

## Key Features

- Product management with abstract `Product` base class
- Perishable and non-perishable product support
- Supplier management with reliability scoring and lead time
- Sales recording with automatic stock updates and transaction history
- Forecasting using moving averages and trend analysis
- Alerts for low stock and near-expiry items
- Backup and restore support for system recovery
- Persistent data storage via CSV files and binary backup
- Central `InventoryManager` controller using `std::map`, `std::vector`, `std::queue`, and `std::set`

## Technology Stack

- Language: C++98
- Compiler: `g++` with `-std=c++98`
- Build tool: GNU Make
- Data storage: CSV files and binary backup
- Target platform: Linux / Unix compatible

## Project Structure

```
RetailForge/
├── main.cpp
├── product.h
├── product.cpp
├── supplier.h
├── supplier.cpp
├── salestransaction.h
├── salestransaction.cpp
├── inventorymanager.h
├── inventorymanager.cpp
├── Makefile
├── products.csv
├── suppliers.csv
├── transactions.csv
├── forecast.csv
├── sales.log
├── backup.dat
├── README.md
├── PROJECT_SUMMARY.txt
├── USAGE_GUIDE.txt
├── IMPLEMENTATION_GUIDE.sh
└── test_and_demo.sh
```

## Core Modules

- `Product Management` — handles product creation, updates, deletion, and searching
- `Supplier Management` — manages supplier records and performance data
- `Sales` — records sales and purchases, updates inventory, logs transactions
- `Reports` — low stock, near expiry, sales ranking, supplier performance
- `Forecasting` — demand prediction and reorder suggestions
- `Backup/Restore` — save and restore system state from binary file

## Main Classes

- `InventoryManager` — central controller for products, suppliers, sales, forecasts, and alerts
- `Product` (abstract) — base class for product metadata and inventory operations
- `PerishableProduct` — extends `Product` with expiry date and shelf life
- `NonPerishableProduct` — extends `Product` with batch number and warranty
- `Supplier` — supplier data model with contact, lead time, and reliability
- `SalesTransaction` — sale/purchase record with transaction details

## Build and Run

### Prerequisites

- `g++` with C++98 support
- GNU Make
- Linux / Unix shell environment

### Build

```bash
cd /workspaces/RetailForge
make clean
make
```

### Run

```bash
./retailforge
```

## Data Files

- `products.csv` — product inventory catalog
- `suppliers.csv` — supplier master data
- `transactions.csv` — transaction history for forecasting
- `forecast.csv` — forecast output and historical demand data
- `sales.log` — append-only sales and purchase audit log
- `backup.dat` — binary backup file for restore operations

## Usage Summary

The console interface presents the following main menu options:

1. Product Management
2. Supplier Management
3. Sales & Purchases
4. Reports & Analytics
5. Forecasting & Alerts
6. System Backup/Restore
0. Exit

The menu-driven CLI supports adding, viewing, searching, and updating products and suppliers, recording sales, generating reports, predicting demand, and creating system backups.

## Notes

- The system uses `std::map` for product and supplier lookups, `std::vector` for sales history, `std::queue` for alerts, and `std::set` for category tracking.
- The code is implemented in clean, modular C++98 style with no external dependencies.
