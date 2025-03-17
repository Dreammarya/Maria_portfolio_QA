# Home Work: Requirements

## The Software
You will test a webshop, which can be found here: [GroceryMate](https://grocerymate.masterschool.com/)

The webshop has the following basic functionalities:
- Register and login functionality
- Searching for products, sorting on price, categories of products
- Add products to favorites
- Add products to the basket
- Check-out process: billing and sending information in a form, choose payment method, calculation of costs (calculate total price)

## New Features

### 1. Product Rating System
**Requirement:** Users should be able to rate products with a 5-star system and have the option to add written feedback.

**Questions:**
- How should the system handle incomplete or missing ratings (e.g., submitting without a star rating or without text feedback)?
- What restrictions apply to written feedback (e.g., character limits, prohibited words, review moderation)?
- Can users edit or delete their ratings after submission, and how is this reflected in the overall product rating?
- Who can rate the product?

**Detailed Requirement:**
- Only users who have purchased the product can submit a rating; otherwise, an informational pop-up appears.
- A rating (stars) is mandatory, but text feedback is optional.
- If a user does not provide a star rating, they cannot submit a review.
- Text feedback is limited to 100 characters.
- Any language is allowed, and there is no moderation.

---

### 2. Age Verification for Alcoholic Products
**Requirement:** Alcoholic products require age verification. A modal should appear when navigating to the alcoholic products category asking if the user is 18+. Users must input their age before accessing the alcoholic products.

**Questions:**
- What happens if a user enters an invalid or incorrect age (e.g., below 18, non-numeric input)?
- Does the system display a specific error message for different invalid inputs?
- Is there a limit on the number of failed attempts before access is restricted?
- Does the age verification modal appear again if the user refreshes the page or navigates back later?
- If the page is refreshed, does the system remember the user's previous input?
- Is the age verification requirement different based on user location due to regional legal restrictions?

**Detailed Requirement:**
- When a user enters the alcoholic product section, a modal appears asking for age confirmation.
- Users must enter their birthdate manually (DD/MM/YYYY).
- If the user is under 18, access to alcoholic products is blocked, and an error message is displayed.
- If the user enters non-numeric input or an incorrect format, an error message should prompt them to enter a valid date.
- Once verified, the user should not have to confirm age again in the same session.
- If the session expires, age verification is required again.
- The system should comply with relevant legal regulations regarding age verification and user data storage.

---

### 3. Shipping Cost Changes
**Requirement:** Free shipping for orders above a certain amount. Orders below this amount will incur a shipping fee.

**Questions:**
- How does the system handle edge cases like applying discounts that bring an order below the free shipping threshold?
- Is the shipping cost updated dynamically in the cart/checkout when items are added or removed?
- Are there different rules for free shipping based on delivery location, item weight, or promotional events?

**Detailed Requirement:**
- If an order total exceeds **X€**, shipping is free.
- If the order total is below **X€**, a standard shipping fee of **Y€** applies.
- Discounts, vouchers, or promotional codes may affect the total price and impact free shipping eligibility.
- Free shipping rules may vary based on delivery location, item weight, or special promotions.
