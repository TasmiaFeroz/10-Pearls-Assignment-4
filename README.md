API Testing with Postman - Assignment No. 4
 
This repository contains a Postman Collection for Assignment No. 4 – API Testing with Postman, demonstrating comprehensive API testing using the Simple Books API. The collection implements multiple HTTP methods, dynamic variable handling, Chai assertions, and API chaining as per the assignment requirements.
Status: ✅ Completed & Submitted

📋 Project Overview
This project fulfills the requirements of Assignment No. 4 – API Testing with Postman. It includes a Postman collection that tests the Simple Books API using GET, POST, PUT, PATCH, and DELETE methods, with dynamic request generation, response parsing, and test assertions, including an intentional failing test case. The collection leverages environment variables and scripting for API chaining and dynamic testing.
Due Date: October 17, 2025 @ 11:55 PM
Submitted by: Tasmia Feroz

🎯 Learning Objectives Achieved


















































ObjectiveStatusImplementationCreate & manage Postman collections✅1 Collection, 5 RequestsVariable handling & scripting✅baseUrl, orderId, customerName variablesAPI chaining & dynamic testing✅Order creation → Update → DeleteAll HTTP methods✅GET, POST, PUT, PATCH, DELETERandom request body generation✅Random customerName generationJSON response parsing & logging✅Parsed orderId & logged responsesChai assertions (including failing case)✅5+ assertions, 1 intentional failPre-request & Tests scripting✅Dynamic customerName in Pre-request

🚀 Quick Start

Import Collection
bashFile → Import → [Drag `Tasmia_Feroz_Assignment_4.json`]

Setup Environment

Create a new environment in Postman
Set baseUrl: https://simple-books-api.glitch.me
Save the environment


Run Collection
bashRunner → Select `Assignment No. 4 – API Testing with Postman` → Run

View Results

Tests should mostly PASS (1 intentional fail)
Check Tests tab and console logs for details




📁 Repository Structure
text📁 api-testing-postman-assignment-4/
├── 📄 README.md                    # This file
├── 📄 Tasmia_Feroz_Assignment_4.json     # Postman Collection
├── 📄 Books-API-Testing.postman_environment.json   # Environment File
├── 📁 screenshots/                       # Visual Proof
│   ├── collection-overview.png
│   ├── test-results.png
│   ├── api-chaining.png
│   └── failing-assertion.png
└── 📄 demo.gif                          # Animated Demo

🔧 API Endpoints Tested









































HTTP MethodEndpointPurposeStatusGET/booksRetrieve all books✅POST/ordersCreate a new order✅PUT/orders/{orderId}Update order customer name✅PATCH/orders/{orderId}Update order status✅DELETE/orders/{orderId}Delete order✅
Base API: Simple Books API

💡 Key Features Implemented
1. Dynamic Variables
javascript// Pre-request Script (POST - Create Order)
const randomName = `Customer_${Math.floor(Math.random() * 1000)}`;
pm.environment.set("customerName", randomName);
2. Random Request Body
json{
  "bookId": 1,
  "customerName": "{{customerName}}"
}
3. JSON Response Parsing
javascript// Tests Script (POST - Create Order)
const jsonData = pm.response.json();
pm.environment.set("orderId", jsonData.orderId);
console.log("Order Created:", jsonData);
4. Chai Assertions
javascript// PASSING TEST (GET - Get All Books)
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});

// FAILING TEST (PATCH - Update Order Status)
pm.test("Failing Case Example", function () {
    pm.expect(pm.response.responseTime).to.be.below(100); // Intentional fail
});
5. API Chaining
textPOST /orders → Save `orderId` → PUT /orders/{orderId} → PATCH /orders/{orderId} → DELETE /orders/{orderId}

🧪 Test Results Summary















































CategoryTotalPassedFailedNotesStatus Codes550200/201/204Response Time101Intentional fail (<100ms)JSON Validation550Parsed correctlyChai Assertions651Intentional fail in PATCHOverall1615193.75%

📸 Screenshots















Collection OverviewTest ResultsAPI ChainingFailed to load imageView linkFailed to load imageView linkFailed to load imageView link

🎓 What I Learned

Variable Management: Using environment variables for dynamic testing.
Pre-request Scripts: Generating random data before requests.
Test Assertions: Writing both passing and failing assertions for robust testing.
API Chaining: Linking requests using response data (e.g., orderId).
Console Logging: Debugging API responses effectively.
HTTP Methods: Practical application of GET, POST, PUT, PATCH, and DELETE.


🔗 Resources Used

Postman University Course
Simple Books API
REST Countries API
RESTful API Guide


📝 Submission Details
Assignment: API Testing with Postman - Assignment No. 4
Due Date: October 17, 2025 @ 11:55 PM
Status: ✅ Submitted
Format: Postman Collection JSON + GitHub Repository
Submitted by: Tasmia Feroz

👩‍💻 Author
Name: Tasmia Feroz
Course: Introduction to API Testing with Postman
Organization: 10Pearls University

📄 License
This project is licensed under the MIT License - see the LICENSE file for details.

⭐ Star this repository if it helped you!
💬 Questions? Open an Issue or contact me directly.

Last Updated: October 17, 2025
Collection Version: 1.0.0

Download Postman Collection
Import Environment


"Good tests catch bugs; great tests build confidence!"
- API Testing Wisdom"
