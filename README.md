### 💼 Project Title

FinTech API Testing With Swagger Documents.

### 📝 Project Description

A simple Node.js-based FinTech API for user account management including deposit, withdraw, transfer, and viewing transactions. The main theme of this project is to verify that the API responses, performance and identify the failure for the HTTP request methods GET and POST.

### 🚀 Features of API

- Create users
- Check user balance
- Deposit funds
- Withdraw funds
- Transfer money between users
- View transaction history
- Swagger UI documentation at /api-docs

### 🔗 FinTech API with Swagger document base URL

This url only run locally not for the public. That means this url is private. 
```
http://localhost:3000/api-docs
```

### 📜 Example Endpoints

```
POST /users - Create a new user

GET /users/:id/balance - Get balance of a user

POST /users/:id/deposit - Deposit money to a user account

POST /users/:id/withdraw - Withdraw money from a user account

POST /transfer - Transfer money from one user to another

GET /users/:id/transactions - View transaction history of a user
```

### ⚙️ Steps to run the API using JMeter

- Open the Jmeter
- Create a **Thread group** in the **Test Plan**
- Set up the **Threads (Users)**,  **Ramp-up-period** and **loop count**
- Add **Header Manager** in the **Thread Group** for added header information
- Create 6 **HTTP Request Sampler** for each end points in the **Thread Group**
- Added **Response Assertion** into each **HTTP Request Sampler** for test the **Status code**
- Added **Constant Timer** in the first **HTTP Request Sampler** and **Uniform Random Timer** in the **Thread Group** for add delay between requests.
- Added 3 types of **Listener** (View Results Tree, Summary Report and View Results in Table) in the **Thread Group** for view the test results
- Finally Run the **Test Plan** and view the results.

### 🗂️ Project Structure

```
│
├── Test Plan # Main container
├── Thread Group # For create virtual user
├── Header Manager # Add Header info
└── Sampler # For sending request to server
└── Timer # Add delay between request
└── Assertion # Check the Response or Request
└── Listener # View Results
```
 
### 📈 Test Results

**View Results Tree:**

1. Resonse data:

![1st image](./Image/view%20results%20tree%20for%20create%20users_Response%20data%20(POST).PNG)

2. Assertion Result:

![2nd image](./Image/view%20results%20tree%20for%20create%20users_Assertion%20Result%20(POST).PNG)

3. All Result:

![3rd image](./Image/view%20results%20tree_all%20request%20results.PNG)

**View Results in Table:**

![1st image](./Image/view%20results%20in%20table.PNG)

**Summary Report:**

![3rd image](./Image/summary%20report.PNG)

### 🔎 Observations

- Status code are not expected for Create users (POST /users).
    - Expcted Status Code: 201
    - Response Staus Code: 200
    - Test Result: Failed

- Performance are well. Every request (user) connected with expected time as well as timers (delay time)
    - Total Samles: 18
    - Error Rate (%): 16.67%
    - Throughput (/sec): 1.8/sec



