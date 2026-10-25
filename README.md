# DecisionIQ — AI-Powered Retail Decision Intelligence Platform

A high-performance, enterprise-grade retail intelligence dashboard built with Next.js 14 App Router, TypeScript, Tailwind CSS, and Recharts, faithfully replicating the modern SaaS analytics aesthetic from the supplied design reference.

## 🌟 Key Features & Visual Layout

### 1. Design & Aesthetic (Faithful to Reference)
- **Top Hero Cards**:
  - **Inventory Health**: Segmented fulfillment bar (Fulfilled, Backordered, Substituted), inventory turns ratio (6.4x), service level progress, and step sparkline indicator.
  - **Agent Autonomy**: Dynamic 4-speedometer dial grid (Auto-executed, Approved, Modified, Rejected) with needle rotation and live status pills.
- **KPI Summary Row**: Total Demand Records (7,432,685), Unique Products (28,182), Active Stores (4), Average Demand (18.4 units).
- **Interactive Recharts Visualizations**:
  - Historical Actual Demand vs. Model Forecast line chart with monthly/weekly/daily aggregation and store breakdowns.
  - Discount Coverage breakdown: 1,518,961 matched records (20.44%) vs. unmatched records by retail category.
- **Middle Section Grid**:
  - **Stock Risk by Category**: Category risk bars (Beverages, Frozen, Dry Goods, Household).
  - **Reorder Queue**: SKU status pills (`Auto Placed`, `Awaiting Approval`, `Blocked`).
  - **Top Agent Activities**: Activity badges with trend indicators.
- **SKU Watchlist Table**: Sortable table with SKU, Product, Warehouse, Date Added, Current Stock, Re-Order point, Days of Cover indicator dots, Status badge, and Action links.
- **Data Quality Pipeline**: Real-time validation metrics for negative demand, zero demand, price anomalies, and catalog metadata linkage.

---

## 🧭 Navigation & Modules

| Module | Route | Description |
| :--- | :--- | :--- |
| **Overview Dashboard** | `/` | Complete retail command center with KPIs, gauges, charts, and watchlist |
| **Demand Forecasting** | `/forecasting` | Actual vs. predicted line charts, 7/14/30-day horizon, model metrics (MAPE, RMSE, R²) |
| **Risk Detection** | `/risk` | Prioritized risk table for stockouts, demand spikes, and price discrepancies |
| **Inventory Optimization** | `/inventory` | Scenario optimizer for EOQ, service level targets (90-99.5%), and capital budgets |
| **Data Explorer** | `/explorer` | Searchable, paginated table across 28,182 catalog SKUs and historical demand slices |
| **AI Decision Assistant**| `/ai-assistant` | Conversational retail decision copilot with starter prompts and data-backed citations |
| **Data Quality** | `/data-quality` | Integrity audit rules and violation counters over 7.4M demand points |
| **Platform Settings** | `/settings` | FastAPI host configuration, health check ping, and telemetry controls |

---

## ⚡ FastAPI Backend Integration

The frontend connects directly to your upstream FastAPI server at `http://localhost:8000`.

Configured endpoints:
- `GET /api/dashboard/summary` — High-level KPI metrics & record counts
- `GET /api/dashboard/demand-trend?granularity=month` — Time-series actual & forecasted demand
- `GET /api/dashboard/discount-coverage` — Matched discount record statistics
- `GET /api/dashboard/data-quality` — Anomaly detection audit metrics
- `GET /health` — Service health check & connection status

### Offline Resiliency & Verified Dataset
If the FastAPI server is temporarily disconnected or undergoing updates:
- The UI immediately surfaces a clear connection indicator pill (`● LIVE` vs `● FASTAPI OFFLINE`).
- The application automatically defaults to the verified Phase 1 retail dataset without crashing.
- Users can click the sync button or the **"Retry Connection"** action banner at any time to reconnect.

---

## 🚀 Getting Started

### 1. Installation
```bash
cd "C:\Users\91983\.gemini\antigravity\scratch\decisioniq"
npm install
```

### 2. Start the Development Server
```bash
npm run dev
```
Open [http://localhost:3000](http://localhost:3000) in your browser.

### 3. Production Build
```bash
npm run build
npm run start
```
