# **System Orders API** (System API)

## **Overview**
The **System Orders API** is a MuleSoft **System API** responsible for providing a consistent, reusable interface to the underlying **Orders data store**.

It exposes **CRUD operations** for orders and abstracts **database-specific details** from higher-level **Process** and **Experience APIs**.

This API follows **API-led connectivity** principles and is designed to remain stable even if the underlying database or system changes.

---

## **API Details**

| Attribute | Value |
|---------|------|
| **API Name** | **System Orders API** |
| **Version** | **v1** |
| **Base URI** | **/api/v1** |
| **Media Type** | **application/json** |
| **API Type** | **System API** |

---

## **Responsibilities (System API Scope)**

This API **is responsible for**:
- Direct interaction with the **Orders data source**
- Exposing **system-level CRUD operations**
- Preserving **field-level data fidelity**
- Handling **system-level validations and errors**

This API **does NOT**:
- Apply **orchestration or business logic**
- Aggregate data from multiple systems
- Perform transformation beyond system requirements

---

## **Implementation Status**

| Area | Status |
|----|------|
| **RAML Definition** | ✅  Completed |
| **POST /orders** | 🟡 In Progress |
| **GET /orders/{orderId}** | 🟡 In Progress |
| **PUT /orders/{orderId}** | ⏳ Not Started |
| **DELETE /orders/{orderId}** | ⏳ Not Started |
| **Database Integration** | ⏳ Not Started |
| **Error Handling** | ⏳ Not Started |
| **Security** | ⏳ Not Started |
| **Logging & Monitoring** | ⏳ Not Started |

> **Legend:**  
> ✅ Completed 🟡 In Progress ⏳ Not Started

---

## **RAML Specification**
This API is defined using **RAML 1.0** and includes:
- **Order** data type definition
- CRUD endpoints for order management
- Standard HTTP response codes

---

## **Data Model**

### **Order**
| Field | Type | Required | Description |
|-----|------|----------|------------|
| **orderId** | string | Yes | Unique order identifier |
| **orderName** | string | No | Order name |
| **salesOrderStatus** | string | No | Current order status |
| **totalAmount** | integer | No | Total order amount |
| **purchasedItems** | string | No | Purchased item details |
| **createdDate** | datetime | No | Record creation timestamp |
| **createdBy** | string | No | Creator identifier |
| **updatedDate** | datetime | No | Last update timestamp |
| **updatedBy** | string | No | Last updater identifier |

---

## **Endpoints**

### **Create Order**
**POST** `/orders`

Creates a new order record.

**Request Body**
```json
{
  "orderId": "12345",
  "orderName": "Sample Order",
  "salesOrderStatus": "NEW",
  "totalAmount": 100
}
