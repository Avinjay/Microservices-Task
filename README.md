# Microservices-Task

## Overview
This document provides details on testing various services after running the `docker-compose` file. These services include User, Product, Order, and Gateway Services. Each service has its own endpoints for testing purposes.

---

## Services and Endpoints

### **User Service**
- **Base URL:** `http://localhost:3000`
- **Endpoints:**
  - **List Users:**  
    ```
    curl http://localhost:3000/users
    ```
    Or open in your browser: [http://localhost:3000/users](http://localhost:3000/users)
- **Output**

  
    <img width="324" alt="image" src="https://github.com/user-attachments/assets/1a8a1a17-cb36-470d-9a82-12236fa5fc71" />


---

### **Product Service**
- **Base URL:** `http://localhost:3001`
- **Endpoints:**
  - **List Products:**  
    ```
    curl http://localhost:3001/products
    ```
    Or open in your browser: [http://localhost:3001/products](http://localhost:3001/products)
- **Output**

  
  <img width="271" alt="image" src="https://github.com/user-attachments/assets/43669d7d-f98d-4535-be36-4516d233a43a" />
 

---

### **Order Service**
- **Base URL:** `http://localhost:3002`
- **Endpoints:**
  - **List Orders:**  
    ```
    curl http://localhost:3002/orders
    ```
    Or open in your browser: [http://localhost:3002/orders](http://localhost:3002/orders)
- **Output**

  
  <img width="311" alt="image" src="https://github.com/user-attachments/assets/d6bad8f1-bd10-477d-807c-9b577adc8996" />


---

### **Gateway Service**
- **Base URL:** `http://localhost:3003/api`
- **Endpoints:**
  - **Users:**  
    ```
    curl http://localhost:3003/api/users
    ```
  - **Products:**  
    ```
    curl http://localhost:3003/api/products
    ```
  - **Orders:**  
    ```
    curl http://localhost:3003/api/orders
    ```
  - **Output**
 
    
    <img width="770" alt="image" src="https://github.com/user-attachments/assets/7cf2cd07-6da9-49c3-b0d9-292b0ef5a0da" />


---

## Instructions
1. Start all services using the `docker-compose` file:
   ```
   docker-compose up
   ```
2. Once the services are running, use the above endpoints to verify the functionality.

Happy testing!
