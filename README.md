# Priya Boutique – E-commerce Order Automation

An end-to-end e-commerce order management automation system built with **n8n, Google Sheets, and Gmail**.

The system automates order creation, order-status notifications, payment and delivery follow-ups, customer communication, and admin notifications while maintaining email-sent tracking in Google Sheets.

## 🚀 Project Overview

Priya Boutique uses multiple n8n workflows to automate the lifecycle of an online order.

The workflows work together through **Google Sheets as the central order-management data layer**.

### System Architecture

```text
Customer / New Order
        │
        ▼
┌─────────────────────┐
│ New Order Workflow  │
└─────────┬───────────┘
          │
          ▼
   Google Sheets
          │
          ├───────────────┐
          │               │
          ▼               ▼
┌─────────────────┐ ┌─────────────────────┐
│ Order Status    │ │ Scheduled Monitoring│
│ Workflow        │ │ Workflow            │
└────────┬────────┘ └──────────┬──────────┘
         │                     │
         ▼                     ▼
       Gmail                 Gmail
    Notifications         Notifications
         │                     │
         └──────────┬──────────┘
                    ▼
              Google Sheets