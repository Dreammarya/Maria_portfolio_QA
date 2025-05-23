## https://grocerymate.masterschool.com/
## *1. Product Rating System**
Requirement: Users should be able to rate products with a 5-star system and have the option to add written feedback.User can edit his comments and update it.

### **1.1 Mandatory Star Rating**
**Test Design Technique:** Boundary Value Analysis (BVA), Equivalence Partitioning (EP)  

| Step# | Action                             | Expected Outcome                                       | OK/NOK | URL | Link to Issue |
|-------|------------------------------------|--------------------------------------------------------|--------|-----|---------------|
| 1     | Go to page of purchaced product    | Product details page is displayed                      |    ok  |  https://grocerymate.masterschool.com/product/66b3a57b3fd5048eacb479a1   |               |
| 2     | Click on "Add a comment"          | Review submission form appears                         |     ok  |  https://grocerymate.masterschool.com/product/66b3a57b3fd5048eacb4798f   |               |
| 3     | Leave star rating empty            |                                                        |     ok   |     |               |
| 4     | Click "Submit Review"              | Error message: "Please select a star rating before submitting."(Invalid input for the field 'Rating'. Please check your input.) ok|     |               |               |

### **1.2 Star Rating is clear**
**Test Design Technique:** Use Case Testing 

| Step# | Action                          | Expected Outcome                                      | OK/NOK | URL | Link to Issue |
|-------|---------------------------------|------------------------------------------------------|--------|-----|---------------|
| 1     |After purchace Go to product page              | Product details page is displayed                   |  ok     |     |               |
| 2     | Click on "Write a Review"       | Review submission form appears                      |   ok   |     |               |
| 3     | Verify 5 stars shown                 | Stars are grayed out till user changed it                            |   nok  | https://grocerymate.masterschool.com/product/66b3a57b3fd5048eacb47998    |               |

<img width="888" alt="image" src="https://github.com/user-attachments/assets/dbbc929b-409f-4549-ac7a-a26c785b77b4" />


### **1.3 Review Submission with Valid Input**
**Test Design Technique:** Use Case Testing  

| Step# | Action                          | Expected Outcome                                      | OK/NOK | URL | Link to Issue |
|-------|---------------------------------|------------------------------------------------------|--------|-----|---------------|
| 1     | Go to product page              | Product details page is displayed                   |  ok     |     |               |
| 2     | Click on "Write a Review"       | Review submission form appears                      |   ok   |     |               |
| 3     | Select 4 stars                   | Stars are highlighted                              |   ok  |     |               |
| 4     | Enter "Very tasty!" in feedback  | Input is accepted                                  |   ok    |  https://grocerymate.masterschool.com/product/66b3a57b3fd5048eacb479a1   |               |
| 5     | Click "Submit Review"           | Review is successfully posted under product reviews |     ok   |     |               |
<img width="453" alt="image" src="https://github.com/user-attachments/assets/37fb0b61-d08b-4bc8-97d1-1812f9870324" />
<img width="817" alt="image" src="https://github.com/user-attachments/assets/3d9d84bc-0eac-4b12-a26e-a2ddeb506f20" />

### **1.4 Review Character Limit**
**Test Design Technique:** Boundary Value Analysis (BVA)  

| Step# | Action                             | Expected Outcome                                      | OK/NOK | URL | Link to Issue |
|-------|------------------------------------|------------------------------------------------------|--------|-----|---------------|
| 1     | Go to product page                 | Product details page is displayed                   |    ok    |     |               |
| 2     | Click on "Write a Review"          | Review submission form appears                      |    ok    |     |               |
| 3     | Enter a 501-character review       |                                                     |    ok    | https://grocerymate.masterschool.com/product/66b3a57b3fd5048eacb479a1    |               |
| 4     | Click "Submit Review"              | Error message: "Review cannot exceed 100 characters." |  NOK      |     |   https://github.com/Dreammarya/Maria_portfolio_QA/issues/5            |

---
<img width="1142" alt="image" src="https://github.com/user-attachments/assets/ccc273ec-d115-4ad6-8f6c-adf86d65edb2" />

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
