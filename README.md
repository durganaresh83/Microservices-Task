# Microservices-Task

## Overview
This document provides details on testing various services after running the `docker-compose` file. These services include User, Product, Order, and Gateway Services. Each service has its own endpoints for testing purposes.

# docker-compose.yml
version: '3.8' <br>

services: <br>
  gateway-service: <br>
    build: <br>
      context: ./gateway-service <br>
    ports: <br>
      - "3003:3003" <br>
    networks: <br>
      - app-network <br>

  user-service: <br>
    build: <br>
      context: ./user-service <br>
    ports: <br>
      - "3000:3000" <br>
    networks: <br>
      - app-network <br>

  product-service: <br>
    build: <br>
      context: ./product-service <br>
    ports: <br>
      - "3001:3001" <br>
    networks: <br>
      - app-network <br>
  order-service: <br>
    build: <br>
      context: ./order-service <br>
    ports: <br>
      - "3002:3002" <br>
    networks: <br>
      - app-network <br>

networks: <br>
  app-network: <br>
    driver: bridge <br>

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

    <img width="677" height="372" alt="Screenshot 2025-11-08 145859" src="https://github.com/user-attachments/assets/792c267b-9835-4e6b-912b-8184c61485c8" />
---

### **Product Service**
- **Base URL:** `http://localhost:3001`
- **Endpoints:**
  - **List Products:**  
    ```
    curl http://localhost:3001/products
    ```
    Or open in your browser: [http://localhost:3001/products](http://localhost:3001/products)

    <img width="664" height="410" alt="Screenshot 2025-11-08 145923" src="https://github.com/user-attachments/assets/d639b79d-0ce5-42f7-8234-6b5ef7fd5158" />
---

### **Order Service**
- **Base URL:** `http://localhost:3002`
- **Endpoints:**
  - **List Orders:**  
    ```
    curl http://localhost:3002/orders
    ```
    Or open in your browser: [http://localhost:3002/orders](http://localhost:3002/orders)

    <img width="619" height="384" alt="Screenshot 2025-11-08 151158" src="https://github.com/user-attachments/assets/62358494-a898-487d-8deb-1bc30ec49fa4" />
---

### **Gateway Service**
- **Base URL:** `http://localhost:3003/api`
- **Endpoints:**
  - **Users:**  
    ```
    curl http://localhost:3003/api/users
    ```
    <img width="605" height="342" alt="Screenshot 2025-11-08 150846" src="https://github.com/user-attachments/assets/f3747949-e641-4951-8871-3b0b82adef6a" />

  - **Products:**  
    ```
    curl http://localhost:3003/api/products
    ```
    <img width="536" height="361" alt="Screenshot 2025-11-08 150905" src="https://github.com/user-attachments/assets/7a55a31b-94e3-40b7-ba04-231a5d267f6d" />

  - **Orders:**  
    ```
    curl http://localhost:3003/api/orders
    ```
    <img width="592" height="370" alt="Screenshot 2025-11-08 151130" src="https://github.com/user-attachments/assets/8d824189-2ade-4c8f-8f7f-0219f3e36089" />
---

## Instructions
1. Start all services using the `docker-compose` file:
   ```
   docker-compose up
   ```
   <img width="1097" height="342" alt="Screenshot 2025-11-08 151222" src="https://github.com/user-attachments/assets/38adbc7a-a94a-46c8-b48a-6bf36b37a795" />

2. Once the services are running, use the above endpoints to verify the functionality.

Happy testing!
