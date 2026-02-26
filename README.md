# n8n-marketplace-monitoring-framework
Reusable multi-user marketplace monitoring architecture built in n8n
# Multi-User Marketplace Monitoring Framework for n8n

Reusable multi-user marketplace monitoring architecture built in n8n.

This project demonstrates how to build a scalable Telegram-based monitoring system with database persistence, deduplication logic, and scheduled execution.

---

## 🚀 Core Architecture

- Telegram UX Layer (multi-user command parsing & validation)
- Database-backed search storage
- Dynamic GraphQL query builder
- Scheduled monitoring engine
- Database-level deduplication (olx_id + telegram_id)
- Delivery-state protection (NULL → TRUE logic)
- 6-hour anti-spam filtering layer

---

## 💬 Example Commands

```
/query iphone 15
/min 2000
/max 3500
```

Each Telegram user can define independent searches.

---

## ⚙️ Monitoring Logic

1. Retrieve active searchers  
2. Build dynamic GraphQL request  
3. Fetch marketplace data  
4. Normalize & split listings  
5. Sort by created_time  
6. Filter last 6 hours  
7. Upsert into marketplace_listings  
8. Retrieve listings where sent_to_telegram IS NULL  
9. Send to Telegram  
10. Mark sent_to_telegram = true  

---

## 🧠 Design Principle

The example implementation uses OLX as a sample API, but the architecture is fully adaptable to other marketplace APIs.

Only the HTTP request and field mappings need modification.

---

## 📦 Status

This repository contains the architecture overview and documentation.

Full workflow JSON and extended documentation available separately.

## 📸 Example Output
<img width="509" height="416" alt="Zrzut ekranu 2026-02-26 173923" src="https://github.com/user-attachments/assets/739dcf4d-29e5-499f-9ec7-0778c7e15b5e" />

<img width="505" height="239" alt="Zrzut ekranu 2026-02-26 173905" src="https://github.com/user-attachments/assets/c2424a39-3e73-4681-bda8-4a5152be3cf2" />

<img width="501" height="147" alt="Zrzut ekranu 2026-02-26 173914" src="https://github.com/user-attachments/assets/583c2d56-3a29-4dfa-95ef-6e6a08f1f9d1" />

<img width="511" height="257" alt="Zrzut ekranu 2026-02-26 174001" src="https://github.com/user-attachments/assets/4fe08f24-5db6-4417-a09a-402c0d2bcecc" />

