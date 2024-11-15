# Experiment-1.1
## 1. Aim/Overview of the practical: 
### Write JavaScript to validate the following fields of the Registration page.
    1. First Name (Name should contains alphabets and the length should not be less than 6 characters).
    2. Password (Password should not be less than 6 characters length).
    3. E-mail id (should not contain any invalid and must follow the standard pattern name@domain.com)
    4. Mobile Number (Phone number should contain 10 digits only).
    5. Last Name and Address (should not be Empty).
### 2. Task to be done: 
 Design a static web page using HTML tags and use the CSS features with different layouts as per need of applications also Use JavaScript for designing dynamic web pages and client- side validation.
### 3. Apparatus: HTML, CSS and JAVASCRIPT

### 4. Steps for experiment/practical:

To validate the specified fields of a registration page using HTML, CSS, and JavaScript, follow these steps:
I.	Create the form structure with the required fields.
II.	Style the form using CSS.
III.	Add JavaScript for form validation.
IV.	HTML: Defines the form fields and includes the necessary id attributes for targeting elements in JavaScript.
V.	CSS: Styles the form to make it visually appealing.
VI.	JavaScript: Adds an event listener to the form to handle form submission, validate the fields, and display error messages or a success message.
### 	The validation checks include:
•	First Name: Must contain only alphabets and be at least 6 characters long.
•	Last Name: Must not be empty.
•	Password: Must be at least 6 characters long.
•	Email: Must follow the standard email pattern.
•	Mobile Number: Must contain exactly 10 digits.
•	Address: Must not be empty.
If any validation fails, an error message is displayed. If all validations pass, a success message is shown.
### 5: Program code:
### HTML code:

 <!DOCTYPE html>
  <html lang="en">
  <head>
   <meta charset="UTF-8">
   <meta name="viewport" content="width=device-width, initial-scale=1.0">
   <title> Registration Form
   </title>
   <link rel="stylesheet" type="text/css" href="beauty.css">
   <style>
     .password-container {
	            position: relative;
	            display: flex;
	            align-items: center;
	        }
	        .toggle-password {
          position: absolute;
	            right: 10px;
	            cursor: pointer;
	        }
	        .error {
	            color: red;
	            font-size: 0.9em;
	        }
	    </style>
	</head>
	<body>
	    <div class="container">
	        <h2>Registration Form</h2>
	        <form id="registrationForm" method="POST" action="register.php" onsubmit="return validateForm()">
	            <!-- Form fields -->
	            <div>
	                <label for="firstName">First Name:</label>
	                <input type="text" id="firstName" name="firstName" oninput="capitalizeFirstLetter(this)" pattern="[A-Za-z]+" title="Only alphabetic characters allowed" required>
	                <span class="error" id="firstNameError"></span>
	            </div>
	
	            <div>
	                <label for="lastName">Last Name:</label>
	                <input type="text" id="lastName" name="lastName" oninput="capitalizeFirstLetter(this)" pattern="[A-Za-z]+" title="Only alphabetic characters allowed" required>
	                <span class="error" id="lastNameError"></span>
	            </div>
	
	            <div>
	                <label for="email">Email:</label>
	                <input type="email" id="email" name="email" required>
	                <span class="error" id="emailError"></span>
	            </div>
	
	            <div class="password-container">
	                <label for="password">Password:</label>
	                <input type="password" id="password" name="password" required>
	                <span class="toggle-password" onclick="togglePasswordVisibility()">👁️</span>
	                <span class="error" id="passwordError"></span>
	            </div>
	            <br>
	            <div> 
	                Gender: 
	                Male <input type="radio" name="mygender" value="male" required> 
	                Female <input type="radio" name="mygender" value="female"> 
	                Other <input type="radio" name="mygender" value="other">
	            </div>
	            <br>
	
	            <div>
	                <label for="phone">Phone Number:</label><br>
	                <input type="tel" id="phone" name="phone" placeholder="1234567890" required oninput="validatePhoneNumber(this)"><br><br>
	                <span class="error" id="phoneError"></span>
	            </div>
	
	            <div>
	                <label for="address">Address:</label>
	                <textarea id="address" name="address" placeholder=" " oninput="validateAddress(this)" required></textarea>
	                <span class="error" id="addressError"></span>
	            </div>
	
	            <div>
	                <button type="submit">Register</button>
	                <button type="reset">Reset</button>
	            </div>
        </form>
	    </div>
	    <script src="logic.js"></script>
	</body>
	</html>

### CSS code:

1.	body {
2.	font-family: sans-serif;
3.	background-image: url('https://img.freepik.com/free-vector/copy-space-bokeh-spring-lights-background_52683-55649.jpg?w=900&t=st=1722422035~exp=1722422635~hmac=fa177a9e796024acec63890a4d76730238e35b9d8da710a944b3e14d10ab51e2');
4.	background-size: cover;
5.	background-repeat: no-repeat;
6.	background-attachment: fixed;
7.	}

8.	.container {
9.	width: 400px;
10.	margin: 50px auto;
11.	padding: 20px;
12.	border: 1px solid #ccc;
13.	border-radius: 5px;
14.	background-color: rgba(255, 255, 255, 0.9); /* Slightly opaque background */
15.	}

16.	input[type="text"],
17.	input[type="email"],
18.	input[type="password"],
19.	input[type="tel"],
20.	textarea {
21.	width: 100%;
22.	padding: 10px;
23.	margin: 10px 0;
24.	border: 1px solid #ccc;
25.	border-radius: 3px;
26.	}

27.	button {
28.	background-color: #4CAF50;
29.	color: white;
30.	padding: 10px 20px;
31.	border: none;
32.	border-radius: 3px;
33.	cursor: pointer;
34.	margin-right: 10px;
35.	}

36.	button[type="reset"] {
37.	background-color: #f44336;
38.	}

39.	.error {
40.	color: red;
41.	font-size: 12px;
42.	margin-bottom: 10px;
43.	}

### JAVASCRIPT code:

1.	function capitalizeFirstLetter(inputField) {
2.	const value = inputField.value;
3.	if (value.length > 0) {
a.	inputField.value = value.charAt(0).toUpperCase() + value.slice(1).toLowerCase();
4.	}
5.	}

6.	function togglePasswordVisibility() {
7.	const passwordInput = document.getElementById('password');
8.	const passwordType = passwordInput.type === 'password' ? 'text' : 'password';
9.	passwordInput.type = passwordType;
10.	}

11.	function validatePhoneNumber(inputField) {
12.	const value = inputField.value;
13.	const validValue = value.replace(/[^0-9]/g, ''); // Only allow digits
14.	if (validValue.length < 10) {
a.	document.getElementById('phoneError').innerText = 'Phone number must be at least 10 digits';
15.	} else {
a.	document.getElementById('phoneError').innerText = '';
16.	}
17.	inputField.value = validValue;
18.	}

19.	function validateAddress(inputField) {
20.	const value = inputField.value;
21.	const validValue = value.replace(/[^A-Za-z0-9\s,.\-]/g, ''); // Allow letters, digits, spaces, commas, periods, and hyphens
22.	if (validValue !== value) {
a.	document.getElementById('addressError').innerText = 'Address can only contain alphanumeric characters, spaces, commas, periods, and hyphens';
23.	} else {
a.	document.getElementById('addressError').innerText = '';
24.	}
25.	inputField.value = validValue;
26.	}

27.	function validateForm() {
28.	let isValid = true;

29.	// Validate First Name
30.	if (!document.getElementById('firstName').value.match(/^[a-zA-Z]+$/)) {
a.	document.getElementById('firstNameError').textContent = 'First name should contain alphabets.';
b.	isValid = false;
31.	} else {
a.	document.getElementById('firstNameError').textContent = '';
32.	}

33.	// Validate Last Name
34.	if (document.getElementById('lastName').value.trim() === '') {
a.	document.getElementById('lastNameError').textContent = 'Last name cannot be empty.';
b.	isValid = false;
35.	} else {
a.	document.getElementById('lastNameError').textContent = '';
36.	}

37.	// Validate Email
38.	if (!document.getElementById('email').value.match(/^\S+@\S+\.\S+$/)) {
a.	document.getElementById('emailError').textContent = 'Please enter a valid email address.';
b.	isValid = false;
39.	} else {
a.	document.getElementById('emailError').textContent = '';
40.	}

41.	// Validate Password
42.	if (document.getElementById('password').value.length < 6) {
a.	document.getElementById('passwordError').textContent = 'Password must be at least 6 characters long.';
b.	isValid = false;
43.	} else {
a.	document.getElementById('passwordError').textContent = '';
44.	}

45.	// Validate Phone Number
46.	if (!document.getElementById('phone').value.match(/^\d{10}$/)) {
a.	document.getElementById('phoneError').textContent = 'Phone number must be 10 digits long.';
b.	isValid = false;
47.	} else {
a.	document.getElementById('phoneError').textContent = '';
48.	}

49.	// Validate Address
50.	if (document.getElementById('address').value.trim() === '') {
a.	document.getElementById('addressError').textContent = 'Address cannot be empty.';
b.	isValid = false;
51.	} else {
a.	document.getElementById('addressError').textContent = '';
52.	}

53.	return isValid;
54.	}function capitalizeFirstLetter(inputField) {
55.	const value = inputField.value;
56.	if (value.length > 0) {
57.	inputField.value = value.charAt(0).toUpperCase() + value.slice(1).toLowerCase();
58.	}
59.	}

60.	function togglePasswordVisibility() {
61.	const passwordInput = document.getElementById('password');
62.	const passwordType = passwordInput.type === 'password' ? 'text' : 'password';
63.	passwordInput.type = passwordType;
64.	}

65.	function validatePhoneNumber(inputField) {
66.	const value = inputField.value;
67.	const validValue = value.replace(/[^0-9]/g, ''); // Only allow digits
68.	if (validValue.length < 10) {
69.	document.getElementById('phoneError').innerText = 'Phone number must be at least 10 digits';
70.	} else {
71.	document.getElementById('phoneError').innerText = '';
72.	}
73.	inputField.value = validValue;
74.	}

75.	function validateAddress(inputField) {
76.	const value = inputField.value;
77.	const validValue = value.replace(/[^A-Za-z0-9\s,.\-]/g, ''); // Allow letters, digits, spaces, commas, periods, and hyphens
78.	if (validValue !== value) {
79.	document.getElementById('addressError').innerText = 'Address can only contain alphanumeric characters, spaces, commas, periods, and hyphens';
80.	} else {
81.	document.getElementById('addressError').innerText = '';
82.	}
83.	inputField.value = validValue;
84.	}

85.	function validateForm() {
86.	let isValid = true;

87.	// Validate First Name
88.	if (!document.getElementById('firstName').value.match(/^[a-zA-Z]+$/)) {
89.	document.getElementById('firstNameError').textContent = 'First name should contain alphabets.';
90.	isValid = false;
91.	} else {
92.	document.getElementById('firstNameError').textContent = '';
93.	}

94.	// Validate Last Name
95.	if (document.getElementById('lastName').value.trim() === '') {
96.	document.getElementById('lastNameError').textContent = 'Last name cannot be empty.';
97.	isValid = false;
98.	} else {
99.	document.getElementById('lastNameError').textContent = '';
100.	}

101.	// Validate Email
102.	if (!document.getElementById('email').value.match(/^\S+@\S+\.\S+$/)) {
103.	document.getElementById('emailError').textContent = 'Please enter a valid email address.';
104.	isValid = false;
105.	} else {
106.	document.getElementById('emailError').textContent = '';
107.	}

108.	// Validate Password
109.	if (document.getElementById('password').value.length < 6) {
110.	document.getElementById('passwordError').textContent = 'Password must be at least 6 characters long.';
111.	isValid = false;
112.	} else {
113.	document.getElementById('passwordError').textContent = '';
114.	}

115.	// Validate Phone Number
116.	if (!document.getElementById('phone').value.match(/^\d{10}$/)) {
117.	document.getElementById('phoneError').textContent = 'Phone number must be 10 digits long.';
118.	isValid = false;
119.	} else {
120.	document.getElementById('phoneError').textContent = '';
121.	}

122.	// Validate Address
123.	if (document.getElementById('address').value.trim() === '') {
124.	document.getElementById('addressError').textContent = 'Address cannot be empty.';
125.	isValid = false;
126.	} else {
127.	document.getElementById('addressError').textContent = '';
128.	}

129.	return isValid;
130.	}


10. Result/Output/Writing Summary:
Here, successfully created registration form created using HTML, CSS, and JavaScript. This example includes a form with basic fields like first name, last name, email, phone number, gender and password, along with a submission handler that validates the input.

### 11. Implementation/Output:
•	Validation of Registration form:
![image](https://github.com/user-attachments/assets/3be90963-d1b6-4459-99d1-3fefb5241446)

•	After registering the form, it will take you to the another browser for printing the thankyou message:
![image](https://github.com/user-attachments/assets/a2802610-d2d8-4dde-9bef-b88ec3720199)


 
