# 📊 EMEA India Team Performance Dashboard - FY2027

Interactive ranking dashboard for India EMEA Tableau Technical Support engineers.

## 🌐 Live Dashboard

**https://dgunani-sudo.github.io/emea-dashboard-fy2027/**

## ✨ Throughput Formula

**Correct Formula:**
```
For each week:
  weekly_throughput = closures_in_week ÷ 5 (working days)

Overall throughput:
  average of all weekly throughputs
```

**Example:**
- Week 1: 15 closures ÷ 5 = 3.0
- Week 2: 14 closures ÷ 5 = 2.8
- Week 3: 9 closures ÷ 5 = 1.8
- Week 4: 10 closures ÷ 5 = 2.0
- **Average throughput: (3.0 + 2.8 + 1.8 + 2.0) ÷ 4 = 2.4**

**Target: ≥ 1.7**

## 📈 Key Metrics

| Metric | Description |
|--------|-------------|
| **Throughput** | Avg of (weekly closures ÷ 5 working days) |
| **CSAT** | Average rating from **case surveys only** (chat excluded) |
| **TTR** | Time to Resolution (days) - **Weighted Average**: `sum(Age×Cases) / sum(Cases)` |
| **SLA%** | Initial response SLA compliance |
| **Reopen%** | Case reopen rate |

## 🎯 Data Source

- **Salesforce OrgCS Dashboard**: 01ZHx000000kpvZMAQ
- **Period**: FY2027 YTD (Feb 1, 2026 - July 10, 2026)
- **Engineers**: 28 (across 3 managers)
- **CSAT**: Case surveys only (Support Survey record type)

## 👥 Teams

- **Kiran Vijay**: 12 engineers
- **Akanksha Saxena**: 13 engineers  
- **Prakash Venugopal**: 3 engineers (Principal SEs)

## 🔧 Features

- ✅ Interactive filters (Manager, Title/Level)
- ✅ Live search
- ✅ Sortable columns
- ✅ Correct throughput (closures ÷ 5, avg all weeks)
- ✅ Case-only CSAT data

---

🤖 Generated with Claude Code
