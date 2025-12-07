# Javascript exercises for React Developers

## SECTION 1 — Conditional Logic & Rendering (10 exercises)

**1. Even or Odd**  
Write a function that receives a number and returns "even" or "odd".

function evenOrOdd(n) {
    return n % 2 === 0 ? "even" : "odd";
}


const evenOrOdd = n => n % 2 === 0 ? "even" : "odd";


**2. Age Gate**  
Create a function that receives an age and returns:
- "minor" if < 18  
- "adult" if >= 18  
- "senior" if >= 60  

function ageGate (age) {
      if (age >= 60) return "senior";
      if (age >= 18) return "adult";
            return "minor";
}

const ageGate = age =>
     age < 18 ? "minor" :
     age < 60 ? "adult" : "senior";


**3. Login Message**  
If a user object has a name, return "Welcome, NAME", otherwise "Welcome, guest".

function loginMessage(user) {
  if (user.name) {
    return "Welcome, " + user.name;
  }
  return "Welcome, guest";
}

const loginMessage = user =>
  user?.name ? `Welcome, ${user.name}` : "Welcome, guest";


**4. Show Price With Discount**  
Given a price and a boolean `isMember`, return the discounted price (10% off for members).

 const priceWithDiscount = (price, isMember) =>
     isMember ? price * 0.9 : price;

function showPriceWithDiscount(price, isMember) {
  if (isMember) {
    return price * 0.9; // 10% de desconto
  }
  return price; // sem desconto
}


**5. Weather Display**
- If temperature < 15 → "Cold"
- If 15–25 → "Mild"
- If > 25 → "Hot"

function weatherDisplay(temperature) {
  if (temperature < 15) {
    return "Cold";
  }
  
  if (temperature <= 25) {
    return "Mild";
  }

  return "Hot";
}

const weatherDisplay = t =>
     t < 15 ? "Cold" : t <= 25 ? "Mild" : "Hot";

**6. Button Text Toggle**  
Given isOpen, return "Close" if true and "Open" if false.

function buttonText(isOpen) {
  if (isOpen) {
    return "Close";
  }
  return "Open";
}

const buttonText = isOpen => isOpen ? "Close" : "Open";

**7. Show Error Message**    
If errorMessage exists, return it. Otherwise return an empty string.

function errorMessage(message) {
  if (message) {
    return message;
  }
  return "";
}

const showError = msg => msg || "";

**8. Stock Check**   
Given quantity, return "In stock" if > 0, otherwise "Out of stock".

function stockCheck(quantity) {
  if (quantity > 0) {
    return "In stock";
  }
  return "Out of stock";
}

const stockCheck = qty => qty > 0 ? "In stock" : "Out of stock";

**9. Show Loading**  
If `isLoading` is `true` → "Loading...", else "Data loaded".

function showLoading(isLoading) {
  if (isLoading) {
    return "Loading...";
  }
  return "Data loaded";
}

const showLoading = isLoading => isLoading ? "Loading..." : "Data loaded";


**10. User Role Message**  
Given a role (“admin”, “user”, “guest”), return a message specific to each.

function userRoleMessage(role) {
  if (role === "admin") {
    return "You have full access.";
  }

  if (role === "user") {
    return "You have limited access.";
  }

  if (role === "guest") {
    return "You have guest access.";
  }

  return "Unknown role.";
}


const userRole = role =>
      role === "admin" ? "Admin access" :
      role === "user"  ? "User access" :
      "Guest access";


---

## SECTION 2 — Array Manipulation (React list rendering) (10 exercises)

**11. Filter Adults**  
Given an array of ages, return only those >= 18.

function filterAdults(ages) {
  return ages.filter(age => age >= 18);
}


const filterAdults = ages => ages.filter(a => a >= 18);

**12. Uppercase Names**  
Given an array of strings, return a new array with all names in uppercase.

function uppercaseNames(names) {
  return names.map(name => name.toUpperCase());
}


const uppercaseNames = arr => arr.map(n => n.toUpperCase());

**13. Double Numbers**  
Given [1, 2, 3], return [2, 4, 6].

function doubleNumbers(numbers) {
  return numbers.map(num => num * 2);
}

const doubleNumbers = nums => nums.map(n => n * 2);

**14. Extract Titles**  
Given an array of objects { title: "" }, return only the titles.

function extractTitles(items) {
  return items.map(item => item.title);
}

const extractTitles = arr => arr.map(obj => obj.title);

**15. Find First Completed Task**  
Given tasks with completed: true/false, return the first completed.

function findFirstCompleted(tasks) {
  return tasks.find(task => task.completed === true);
}

 const firstCompleted = tasks =>
    tasks.find(t => t.completed);

**16. Sum of Prices**  
Given [{ price: 10 }, { price: 20 }], return the total price.

const sumPrices = items =>
    items.reduce((sum, item) => sum + item.price, 0);

function sumOfPrices(items) {
  return items.reduce((total, item) => total + item.price, 0);
}

**17. Count Active Users**  
Given users with { active: true/false }, return how many are active.

function countActiveUsers(users) {
  return users.filter(user => user.active).length;
}

const countActive = users =>
  users.filter(u => u.active).length;

**18. Sort Products by Price**    
Given an array of { name, price }, sort them from lowest to highest.

function sortProductsByPrice(products) {
  return products.sort((a, b) => a.price - b.price);
}

const sortByPrice = products =>
  [...products].sort((a, b) => a.price - b.price);

**19. Get Initials**  
"Alexandre Calaça" → "AC".

function getInitials(name) {
  return name
.split(" ")
    .map(word => word[0].toUpperCase())
    .join("");
}

const getInitials = name =>
  name.split(" ").map(w => w[0]).join("").toUpperCase();


**20. Filter by Search Term**  
Given a list of strings and a search text, return only items containing the text.

function filterBySearch(items, searchText) {
    return items.filter(item =>
    item.toLowerCase().includes(searchText.toLowerCase())
  );
}

const searchFilter = (items, term) =>
  items.filter(i => i.toLowerCase().includes(term.toLowerCase()));

---

## SECTION 3 — String & Input Handling (React form-like logic) (5 exercises)
**21. Trim Input**  
Remove leading and trailing spaces from a string.

const trimInput = str => str.trim();


**22. Validate Email**  
Check if a string contains "@" and ".".


const validateEmail = email =>
  email.includes("@") && email.includes(".");

**23. Format Username**  
Convert "Alexandre Calaça" → "alexandre_calaca".

const formatUsername = name =>
  name.toLowerCase().replace(/\s+/g, "_");


**24. Capitalize First Letter**  
"hello" → "Hello".

const capitalize = str =>
  str.charAt(0).toUpperCase() + str.slice(1);


**25. Mask Credit Card**  
"1234567812345678" → "************5678".


const maskCard = card =>
  "*".repeat(card.length - 4) + card.slice(-4);

---

## SECTION 4 — State-Like Transformations (React setState practice) (5 exercises)

**26. Toggle Boolean**  
Given a boolean, return its opposite.

const toggle = b => !b;


**27. Increment Counter**  
Function that receives a counter and returns counter + 1.

const increment = c => c + 1;


**28. Select Option**  
Given a selected value and an array of options, return the matching option.

const selectOption = (value, options) =>
  options.find(o => o === value);


**29. Pagination Slice**  
Given an array, a page number, and a page size, return the correct slice.

const paginate = (arr, page, size) =>
  arr.slice((page - 1) * size, page * size);

**30. Merge User Data**  
Given two objects (e.g., { name: "Alex" } and { age: 30 }), merge them into one.

const mergeUser = (a, b) => ({ ...a, ...b });
