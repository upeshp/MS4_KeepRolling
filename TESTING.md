## Testing

_Code Validators_

All code passed validation tests from the [HTML](https://validator.w3.org/) and [CSS](https://jigsaw.w3.org/css-validator/) validation websites.

For python code, I used the command 'python3 - m flake8' in the gitpod terminal to list out any PEP8 compliance issues: 
- The majority of these have been addressed, any issues remaining are those where it was difficult to change the code without impacting functionality, for example in migrations.py files.

_Speed_

I used [GT Metrix](https://gtmetrix.com/) to analyse the speed of the website, which gave an overall grade of B:
- There are some issues with the loading of the site, whilst there are some potential fixes to improve this, such as restructuring the code so the main image is loaded inline (as opposed to from the css file), as there is no material impact on site performance, and due to timing constraints, this has been left as a bug to fix in future development.

_User Stories_

As a/an| I want to be able to | So that I can | Addressed
------- | -------- | ------- | ------
Shopper | View a list of products | Select some to purchase | "Courses" and "Clothing" links display product listings
Shopper | View individual product details | See the price/description/rating/sizes | Clicking on product card in product listings displays product details
Shopper | View the total of my purchases at any time | Avoid spending too much | Clicking on the "shopping bag" icon displays the current total
Site User | Easily register for account | Have an account/view my profile | Simple registration form on clicking "person" icon
Site User | Easily login/logout | Access my account | Option to login/logout on clicking "person" icon 
Site User | Easily recover my password | Recover access to account | "Forgot password" link on login page enables password reset
Site User | Receive email confirmation after registering | Verify registration successful | Emails setup to send on registration
Site User | Have a personalised user profile | View order history/save payment info | Profile page available after login, shows order history/payment info
Shopper | Search for a product | Find a specific product | Functioning search form included in navbar, can search by name/description
Shopper | Easily see what I've searched for | Quickly decide if what I want is there | Search form returns results listing
Shopper | Select size/qty of product when purchasing | Ensure I don't select wrong product/size | Size/qty selector forms included on individual product page
Shopper | View bag items | See total cost/all items I'll receive | Bag available on clicking "bag" icon, lists products/total spend
Shopper | Adjust qty of items in my bag | Easily make changes to bag before checkout | In bag update/remove items included under qty selector
Shopper | Easily enter payment info | Checkout quickly | Simple form for entering details/card info on checkout form
Shopper | View an order confirmation after checkout | Ensure no mistakes made | Order confirmation on profile page and emailed to user
Store Owner | Add a product | Add new items to store | Admin user is able to add products via form
Store Owner | Edit/update a product | Change product details | Admin user is able to edit products via product listings/product detail pages
Store Owner | Delete a product | Remove items not for sale | Admin user is able to delete products via product listings/product detail pages

_Features_

The following details how the various features of the site have been tested for their intended purpose:

GENERAL

- Top navbar is fixed at the top for all pages
- Navbar changes to burger icon on mobile
    - All navbar links redirect to correct site page
- Footer appears at bottom of homepage
 	- Footer social links all open in new tabs

HOMEPAGE
 
- Button titled COURSES takes you to courses products page
- Button titled CLOTHING takes you to clothing products page
- Search form brings back appropriate results based on name/description

LOGIN

- Entering correct username/password takes you to user profile page/displays correct toast
- Entering incorrect username and/or password displays "Incorrect username and/or password" message 

REGISTER

- Entering username/password in required format completes registration and sends email to confirm registration/displays correct toast
- Entering username/password not matching required format displays prompts to correct

PROFILE

- Profile page displays user details/order history
- Able to edit user details

COURSES/CLOTHING PAGES

- Display appropriate products according to category
- Displayed in card format with image/name/price/rating (if applicable) showing

PRODUCT DETAIL

- Shows individual product details
- Form to select qty/size
- Button to add to bag
- Checkout button takes you to checkout

BAG
 
- Correctly shows all added items/total price
- Ability to add/remove qty of items

CHECKOUT

- Shows form to fill out payment details
- Error message if details entered incorrectly
- Order success message shown when order completed

ADMIN

- Only the admin user profile is able to make add/edit/delete changes to the site products

_Responsiveness_

Specific responsive features included:

- On mobile the navbar menu items are displayed in dropdown icon
- The bag view is displayed differently on mobile
	
I tested the website by changing the screen size on my display, and using the inspect function on developer tools to show how it looks on different devices.

I tested the website on various browsers/devices which were available to me.

It is noted that the homepage image on small screens isn't as visually appealing as on larger screens, as it focuses on the left-hand-side of the image. Also the gap between the hero-image content and the footer is quite narrow on smaller screens. These are bugs for future development, as site functionality is not impacted.

_Bugs_

- No separate html template for courses/clothing, meaning searching brings back all items, regardless of category.
- Homepage image doesn't look ideal on very small screens.
- Navbar menu items on dropdown are quite small/close together on very small screens.
- No custom error 404/500 pages included.
- Loading speed could be improved upon.
- Although the styling has been kept minimal for a simple design, it is recognised further styling could be included to improve presentation of site, for example making more features red like the prices/buttons, or including animation effects for the product cards etc.
- Due to time constraints, the above will not be addressed in this version, but will be addressed in future versions of the site.

