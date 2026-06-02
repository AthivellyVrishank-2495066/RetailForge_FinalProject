# RetailForge Flow Chart

This flowchart shows the main application flow for RetailForge, focusing on the top-level menu and modules.

```mermaid
flowchart TD
    Start([Start]) --> Launch[Launch `./retailforge`]
    Launch --> Load[Load data from CSV files]
    Load --> MainMenu[Display Main Menu]

    MainMenu -->|1| ProductManagement[Product Management]
    MainMenu -->|2| SupplierManagement[Supplier Management]
    MainMenu -->|3| SalesAndPurchases[Sales & Purchases]
    MainMenu -->|4| ReportsAndAnalytics[Reports & Analytics]
    MainMenu -->|5| ForecastingAndAlerts[Forecasting & Alerts]
    MainMenu -->|6| BackupRestore[System Backup/Restore]
    MainMenu -->|0| Exit[Exit application]

    ProductManagement --> SaveData[Save data]
    SupplierManagement --> SaveData
    SalesAndPurchases --> SaveData
    ReportsAndAnalytics --> SaveData
    ForecastingAndAlerts --> SaveData
    BackupRestore --> SaveData

    SaveData --> MainMenu

    Exit --> End([End])
```

## Notes
- The chart is intentionally high-level and shows only the main menu and primary modules.
- Control returns to the main menu after each module completes.
