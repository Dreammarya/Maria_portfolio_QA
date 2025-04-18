## https://grocerymate.masterschool.com/
## *1. Product Rating System**
Requirement: Users should be able to rate products with a 5-star system and have the option to add written feedback.

### **1.1 Mandatory Star Rating**
**Test Design Technique:** Boundary Value Analysis (BVA), Equivalence Partitioning (EP)  

| Step# | Action                             | Expected Outcome                                       | OK/NOK | URL | Link to Issue |
|-------|------------------------------------|--------------------------------------------------------|--------|-----|---------------|
| 1     | Go to page of purchaced product    | Product details page is displayed                      |    ok  |     |               |
| 2     | Click on "Write a Review"          | Review submission form appears                         |     ok  |  https://grocerymate.masterschool.com/product/66b3a57b3fd5048eacb4798f   |               |
| 3     | Leave star rating empty            |                                                        |     ok   |     |               |
| 4     | Click "Submit Review"              | Error message: "Please select a star rating before submitting." ok|     |               |               |


### **1.2 Review Submission with Valid Input**
**Test Design Technique:** Use Case Testing  

| Step# | Action                          | Expected Outcome                                      | OK/NOK | URL | Link to Issue |
|-------|---------------------------------|------------------------------------------------------|--------|-----|---------------|
| 1     | Go to product page              | Product details page is displayed                   |  ok     |     |               |
| 2     | Click on "Write a Review"       | Review submission form appears                      |   ok   |     |               |
| 3     | Select 4 stars                   | Stars are highlighted                              |   ok  |     |               |
| 4     | Enter "Very tasty!" in feedback  | Input is accepted                                  |   ok    |     |               |
| 5     | Click "Submit Review"           | Review is successfully posted under product reviews |     ok   |     |               |
<img width="453" alt="image" src="https://github.com/user-attachments/assets/37fb0b61-d08b-4bc8-97d1-1812f9870324" />
### **1.3 Review Character Limit**
**Test Design Technique:** Boundary Value Analysis (BVA)  

| Step# | Action                             | Expected Outcome                                      | OK/NOK | URL | Link to Issue |
|-------|------------------------------------|------------------------------------------------------|--------|-----|---------------|
| 1     | Go to product page                 | Product details page is displayed                   |    ok    |     |               |
| 2     | Click on "Write a Review"          | Review submission form appears                      |    ok    |     |               |
| 3     | Enter a 101-character review       |                                                     |    ok    |     |               |
| 4     | Click "Submit Review"              | Error message: "Review cannot exceed 100 characters." |        |     |               |

---

## **2. Age Verification for Alcoholic Products**
Requirement: Alcoholic products require age verification. A modal should appear when navigating to the alcoholic products category asking if the user is 18+. Users must input their age before accessing the alcoholic products.

### **2.1 Valid Age Input (Allowed Access)**
**Test Design Technique:** Equivalence Partitioning (EP)  

| Step# | Action                    | Expected Outcome                                      | OK/NOK | URL | Link to Issue |
|-------|---------------------------|------------------------------------------------------|--------|-----|---------------|
| 1     | Navigate to Alcohol category | Age verification modal appears                      |  ok      |     |               |
| 2     | Enter "01/01/2007"         | User is granted access to alcoholic products       |      ok  |     |               |

### **2.2 Invalid Age Input (Blocked Access)**
**Test Design Technique:** Boundary Value Analysis (BVA)  

| Step# | Action                    | Expected Outcome                                      | OK/NOK | URL | Link to Issue |
|-------|---------------------------|------------------------------------------------------|--------|-----|---------------|
| 1     | Navigate to Alcohol category | Age verification modal appears                      |     ok   |     |               |
| 2     | Enter "01/01/2012"         | Error message: "You must be 18+ to access these products." |     ok   |     |               |

### **2.3 Non-Numeric or Incorrect Format Input**
**Test Design Technique:** Error Guessing  

| Step# | Action                    | Expected Outcome                                      | OK/NOK | URL | Link to Issue |
|-------|---------------------------|------------------------------------------------------|--------|-----|---------------|
| 1     | Navigate to Alcohol category | Age verification modal appears                      |    ok    |     |               |
| 2     | Enter "32/15/abcd"         | Error message: "Invalid date format. Please enter DD/MM/YYYY." |   ok     |     |               |

---

## **3. Shipping Cost Changes**
Requirement: Free shipping for orders above a certain amount. Orders below this amount will incur a shipping fee.

### **3.1 Free Shipping Applied for Orders Above Threshold**
**Test Design Technique:** Boundary Value Analysis (BVA)  

| Step# | Action                         | Expected Outcome           | OK/NOK | URL | Link to Issue |
|-------|--------------------------------|----------------------------|--------|-----|---------------|
| 1     | Add items worth 51€ to the cart | Shipping fee = 0€          |   ok     |     |               |

### **3.2 Discounted Shipping for Single Expensive Item**
**Test Design Technique:** Equivalence Partitioning (EP)  

| Step# | Action                          | Expected Outcome                                  | OK/NOK | URL | Link to Issue |
|-------|---------------------------------|--------------------------------------------------|--------|-----|---------------|
| 1     | Add one item worth 15€          | Discounted shipping fee is applied              |   ok     |     |               |

### **3.3 Shipping Cost Updates Dynamically**
**Test Design Technique:** Use Case Testing  

| Step# | Action                              | Expected Outcome                               | OK/NOK | URL | Link to Issue |
|-------|-------------------------------------|-----------------------------------------------|--------|-----|---------------|
| 1     | Add an item to the cart  (in total >51)          | Shipping cost updates based on order total   |    ok    |     |               |
| 2     | Remove an item from the cart  (in total <50)     | Shipping cost updates accordingly            |  ok      |     |               |

---
