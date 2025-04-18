## **Test Case Design**

The test cases designed will test the three new features.
---

## **1. Product Rating System**

**Requirement:** Users should be able to rate products with a 5-star system and have the option to add written feedback.

### **Test Cases:**

#### **1.1 Mandatory Star Rating**
- **Test Design Technique:** Boundary Value Analysis (BVA), Equivalence Partitioning (EP)
- **Test Case:** Verify that a user cannot submit a review without selecting a star rating.
- **Input:** Try to submit a review without selecting stars.
- **Expected Outcome:** Error message "Please select a star rating before submitting."

#### **1.2 Review Submission with Valid Input**
- **Test Design Technique:** Use Case Testing
- **Test Case:** Verify that a user who purchased a product can successfully submit a review
- **Input:** Select 4 stars and enter feedback "very testy!"
- **Expected Outcome:** Review successfully submitted and displayed under product reviews.

#### **1.3 Review Character Limit**
- **Test Design Technique:** Boundary Value Analysis (BVA)
- **Test Case:** Verify that a review cannot exceed 100 characters.
- **Input:** Enter a review with 101 characters.
- **Expected Outcome:** Error message "Review cannot exceed 100 characters."

---

## **2. Age Verification for Alcoholic Products**

**Requirement:** Alcoholic products require age verification. A modal should appear when navigating to the alcoholic products category asking if the user is 18+. Users must input their age before accessing the alcoholic products.

### **Test Cases:**

#### **2.1 Valid Age Input (Allowed Access)**
- **Test Design Technique:** Equivalence Partitioning (EP)
- **Test Case:** Verify that a user who enters a valid age (18+) can access alcoholic products.
- **Input:** Enter "01/01/2007" (user is over 18).
- **Expected Outcome:** User is granted access to alcoholic products.

#### **2.2 Invalid Age Input (Blocked Access)**
- **Test Design Technique:** Boundary Value Analysis (BVA)
- **Test Case:** Verify that a user under 18 is blocked from accessing alcoholic products.
- **Input:** Enter "01/01/2012" (user is less then 18 years old).
- **Expected Outcome:** Error message "You must be 18+ to access these products."

#### **2.3 Non-Numeric or Incorrect Format Input**
- **Test Design Technique:** Error Guessing
- **Test Case:** Verify system behavior when an invalid date format is entered.
- **Input:** Enter "32/15/abcd".
- **Expected Outcome:** Error message "Invalid date format. Please enter DD/MM/YYYY."
---

## **3. Shipping Cost Changes**

**Requirement:** Free shipping for orders above a certain amount. Orders below this amount will incur a shipping fee.

### **Test Cases:**

#### **3.1 Free Shipping Applied for Orders Above Threshold**
- **Test Design Technique:** Boundary Value Analysis (BVA)
- **Test Case:** Verify that free shipping is applied when the order total exceeds the required threshold.
- **Input:** Add items worth 51€ to the cart.
- **Expected Outcome:** Shipping fee = 0€.

#### **3.2 Discounted Shipping for Single Expensive Item**
- **Test Design Technique:** Equivalence Partitioning (EP)
- **Test Case:** Verify that a single item costing more than 10€ receives a discount but does not qualify for free shipping.
- **Input:** Add one item worth 15€.
- **Expected Outcome:** Discounted shipping fee is applied.

#### **3.3 Shipping Cost Updates Dynamically**
- **Test Design Technique:** Use Case Testing
- **Test Case:** Verify that the shipping cost updates dynamically when items are added or removed from the cart.
- **Input:** Add and remove items from the cart, checking the shipping cost update.
- **Expected Outcome:** Shipping cost updates correctly based on total order value.
---
