# Dashboard Optimizations - July 10, 2026

## 🎯 Primary Change: TTR Calculation Formula

### Previous Formula
```javascript
avgTtr = sum(all individual TTRs) / count(engineers)
```
This was a **simple average** that gave equal weight to each engineer regardless of their case volume.

### New Formula (Weighted Average)
```javascript
avgTtr = sum(Age(days) × Cases) / sum(Cases)
```

**Rationale:**
- Matches Salesforce OrgCS Dashboard formula
- Gives proper weight to engineers handling more cases
- More accurate representation of actual team performance
- Formula options provided by stakeholder:
  - `AVG([Age(days)])` OR
  - `sum([Age(days)]) / sum([Time To Resolve Count])`

### Example Impact
**Scenario:** 2 engineers filtered
- Engineer A: 200 cases, 5 days TTR
- Engineer B: 20 cases, 20 days TTR

**Old calculation (simple average):**
```
(5 + 20) / 2 = 12.5 days
```

**New calculation (weighted average):**
```
(200×5 + 20×20) / (200+20) = 1400 / 220 = 6.36 days
```

The weighted average correctly reflects that Engineer A's performance (90% of cases) dominates the metric.

---

## 🎨 Visual Enhancements

### TTR Color Coding
Added intelligent color coding for TTR values in the table:
- **Green (Excellent):** < 7 days
- **Blue (Good):** 7-10 days
- **Orange (Average):** 10-15 days
- **Red (Poor):** > 15 days

### CSS Classes Added
```css
.ttr-excellent {color:#1B5E20; font-weight:700}
.ttr-good {color:#1565C0; font-weight:600}
.ttr-average {color:#E65100; font-weight:600}
.ttr-poor {color:#B71C1C; font-weight:700}
```

---

## 📚 Documentation Updates

### Sidebar "About" Section
Added TTR formula explanation:
```
TTR Formula:
sum(Age × Cases) ÷ sum(Cases)
(Weighted average days)
```

### Column Header Tooltip
Updated TTR column tooltip:
```
"Weighted Avg Time-to-Resolution: sum(Age×Cases) / sum(Cases)"
```

### README.md
Updated metrics table to clarify TTR calculation method.

---

## ✅ Benefits

1. **Accuracy:** TTR now correctly weights high-volume engineers
2. **Alignment:** Matches Salesforce OrgCS Dashboard (01ZHx000000kpvZMAQ)
3. **Visibility:** Color coding makes performance patterns immediately visible
4. **Transparency:** Clear documentation of calculation method
5. **Consistency:** Formula is documented in-app, README, and tooltips

---

## 🔄 Data Source Reference

- **Salesforce Dashboard ID:** 01ZHx000000kpvZMAQ
- **Dashboard Name:** EMEA Dashboard
- **Period:** FY2027 YTD (Feb 1 - July 10, 2026)
- **Data Points:** 28 engineers across 3 managers

---

## 🚀 Next Steps (Optional Future Enhancements)

1. **Per-Engineer TTR Recalculation:** If raw case-level data becomes available, recalculate individual engineer TTRs using the weighted formula
2. **Historical Trending:** Add week-over-week TTR trend visualization
3. **Benchmark Lines:** Add target TTR threshold lines to visualizations
4. **Export Functionality:** Add CSV export with calculated metrics
5. **Real-time Sync:** Connect directly to Salesforce API for live data updates

---

Generated with Claude Code 🤖
