<script>
  import Header from "$lib/components/Header.svelte";
  import Footer from "$lib/components/Footer.svelte";
  import { onMount } from 'svelte';

  let name, creditCardNumber, expirationDate, cvv, dollar;
  let errorMessages = [];

  onMount(() => {
    const form = document.querySelector('form.donation-form');

    form.addEventListener('submit', (event) => {
      event.preventDefault();

      errorMessages = [];

      validateName();
      validateCreditCardNumber();
      validateExpirationDate();
      validateCVV();
      validateDollar();

      if (errorMessages.length > 0) {
        displayErrorMessages();
        return;
      }

      submitForm();
    });

    function validateName() {
      if (!name) {
        errorMessages.push('Please enter your name');
      }
    }

    function validateCreditCardNumber() {
      if (!creditCardNumber || creditCardNumber.length < 16) {
        errorMessages.push('Please enter a valid credit card number');
      }
    }

    function validateExpirationDate() {
      if (!expirationDate) {
        errorMessages.push('Please enter your credit card expiration date');
      }
    }

    function validateCVV() {
      if (!cvv || cvv.length < 3) {
        errorMessages.push('Please enter your credit card CVV');
      }
    }

    function validateDollar() {
      if (!dollar) {
        errorMessages.push('Please enter a donation amount');
      }
    }

    function displayErrorMessages() {
      const errorMessageElement = document.querySelector('.error-messages');
      errorMessageElement.textContent = errorMessages.join('\n');
      errorMessageElement.style.display = 'block';
    }

    function submitForm() {
      console.log('Submitting form...');
    }
  });

</script>

<Header />

<main>
  <section class="page2-sponsor-page">
    <div class="text-area">
      <h2 class="page2-numbers-header page2-sponsor-text">
        Become a <span class="yellow">sponsor</span>
      </h2>
    </div>
    <div class="page2-options-wrapper">
      <div class="page2-options-wrapper">

        <!-- Option 1 -->
        <div class="page2-option page2-option1">
          <svg
            viewBox="0 0 149 198"
            fill="none"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path
              d="M142.515 0.00614879C149.727 0.0915737 149.942 0.333528 147.852 22.5583C143.991 63.6479 139.988 104.595 136.045 145.599C134.83 158.214 133.616 170.828 132.406 183.457C131.2 195.986 130.626 197.808 126.631 197.894C116.059 198.093 105.483 197.951 94.9109 197.951L64.907 197.951L64.907 197.979C45.1876 197.979 25.4724 198.008 5.753 197.965C-0.75149 197.965 -0.93599 196.897 1.26936 176.281C6.61111 126.307 11.9443 76.3336 17.226 26.3029C18.2814 16.2797 20.002 10.1005 23.4258 10.4992C24.846 10.67 26.2748 9.8728 27.7035 9.77314C51.4132 8.13582 75.1228 6.0998 98.8325 5.1174C113.412 4.50519 127.935 -0.193176 142.515 0.00614879Z"
              fill=""
            />
          </svg>
          <div class="options-text-wrapper">
            <!-- Title for Option 1 -->
            <h3 class="black">Option 1</h3>
            <!-- Description for Option 1 -->
            <p class="black">
              Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do
              eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut
              enim ad minim veniam, quis nostrud exercitation ullamco laboris
            </p>
            <!-- Button for Option 1 -->
            <label for="formulier">formulier</label>
          </div>
        </div>
      </div>

      <!-- Option 2 -->
      <div class="page2-option page2-option2">
        <!-- SVG representation for Option 2 -->
        <svg
          viewBox="0 0 149 198"
          fill="none"
          xmlns="http://www.w3.org/2000/svg"
        >
          <path
            d="M142.515 0.00614879C149.727 0.0915737 149.942 0.333528 147.852 22.5583C143.991 63.6479 139.988 104.595 136.045 145.599C134.83 158.214 133.616 170.828 132.406 183.457C131.2 195.986 130.626 197.808 126.631 197.894C116.059 198.093 105.483 197.951 94.9109 197.951L64.907 197.951L64.907 197.979C45.1876 197.979 25.4724 198.008 5.753 197.965C-0.75149 197.965 -0.93599 196.897 1.26936 176.281C6.61111 126.307 11.9443 76.3336 17.226 26.3029C18.2814 16.2797 20.002 10.1005 23.4258 10.4992C24.846 10.67 26.2748 9.8728 27.7035 9.77314C51.4132 8.13582 75.1228 6.0998 98.8325 5.1174C113.412 4.50519 127.935 -0.193176 142.515 0.00614879Z"
            fill=""
          />
        </svg>
        <div class="options-text-wrapper">
          <!-- Title for Option 2 -->
          <h3>Option 2</h3>
          <!-- Description for Option 2 -->
          <p>
            Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do
            eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim
            ad minim veniam, quis nostrud exercitation ullamco laboris
          </p>
          <!-- Button for Option 2 -->
          <label for="formulier">formulier</label>
        </div>
      </div>

      <!-- Option 3 -->
      <div class="page2-option page2-option3">
        <!-- SVG representation for Option 3 -->
        <svg
          viewBox="0 0 149 198"
          fill="none"
          xmlns="http://www.w3.org/2000/svg"
        >
          <path
            d="M142.515 0.00614879C149.727 0.0915737 149.942 0.333528 147.852 22.5583C143.991 63.6479 139.988 104.595 136.045 145.599C134.83 158.214 133.616 170.828 132.406 183.457C131.2 195.986 130.626 197.808 126.631 197.894C116.059 198.093 105.483 197.951 94.9109 197.951L64.907 197.951L64.907 197.979C45.1876 197.979 25.4724 198.008 5.753 197.965C-0.75149 197.965 -0.93599 196.897 1.26936 176.281C6.61111 126.307 11.9443 76.3336 17.226 26.3029C18.2814 16.2797 20.002 10.1005 23.4258 10.4992C24.846 10.67 26.2748 9.8728 27.7035 9.77314C51.4132 8.13582 75.1228 6.0998 98.8325 5.1174C113.412 4.50519 127.935 -0.193176 142.515 0.00614879Z"
            fill=""
          />
        </svg>
        <div class="options-text-wrapper">
          <!-- Title for Option 3 -->
          <h3>Option 3</h3>
          <!-- Description for Option 3 -->
          <p>
            Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do
            eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim
            ad minim veniam, quis nostrud exercitation ullamco laboris
          </p>
          <!-- Button for Option 3 -->
          <label for="formulier">formulier</label>
        </div>
      </div>
    </div>
  </section>

  <input type="checkbox" id="formulier" style="display: none;">


  <!-- Popup for donation form -->
  <div class="popup">
    <form class="donation-form">
      <fieldset>
        <legend>Donate from here</legend>
  
        <div class="form-group">
          <label for="name" class="form-label">Name:</label>
          <input type="text" id="name" class="form-control" on:input={(event) => name = event.detail.value} required />
        </div>
  
        <div class="form-group">
          <label for="creditCardNumber" class="form-label">Credit Card Number:</label>
          <input
            type="number"
            id="creditCardNumber"
            class="form-control"
            on:input={(event) => creditCardNumber = event.detail.value}
            required
          />
        </div>
  
        <div class="form-group">
          <label for="expirationDate" class="form-label">Expiration Date:</label>
          <input
            type="date"
            id="expirationDate"
            class="form-control"
            on:input={(event) => expirationDate = event.detail.value}
            required
          />
        </div>
  
        <div class="form-group">
          <label for="cvv" class="form-label">CVV:</label>
          <input type="number" id="cvv" class="form-control" on:input={(event) => cvv = event.detail.value} required />
        </div>
      </fieldset>
  
      <div class="form-group">
        <label for="option" class="form-label">Select an option:</label>
        <select id="option" class="form-select" on:input={(event) => dollar = event.detail.value} required>
          <option value="1">1</option>
          <option value="2">2</option>
          <option value="3">3</option>
        </select>
      </div>
  
      <div class="form-group">
        <label for="dollar" class="form-label">Donation Amount ($):</label>
        <input type="number" id="dollar" class="form-control" on:input={(event) => dollar = event.detail.value} required />
      </div>
  
      <div class="error-messages" style="display: none;"></div>
  
      <button type="submit" class="form-btn">Donate</button>
    </form>
  </div>
  
  <!-- {/if} -->
</main>

<Footer />

<style>
  /* General form styles */

  input#formulier:checked ~ .popup {
    display: flex;
  }

  label[for="formulier"] {
  background-color: #0055b8;
  color: #fff;
  padding: 10px 20px;
  border: none;
  border-radius: 30px;
  font-size: 16px;
  font-weight: bold;
  cursor: pointer;
}

label[for="formulier"]:hover {
  background-color: #0069d9;
}

@media (max-width: 768px) {
  label[for="formulier"] {
    font-size: 14px;
    padding: 5px 10px;
  }
}
  .popup {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.7);
    color: #000000;
    display: flex;
    align-items: center;
    justify-content: center;
    display:none;
  }

  .popup-title {
    font-size: 24px;
    font-weight: bold;
    margin-bottom: 20px;
  }

  .popup-text {
    font-size: 16px;
    margin-bottom: 20px;
  }

  .popup-close-btn {
    /* Your button styles go here */
    position: absolute;
    top: 10px;
    right: 10px;
    cursor: pointer;
}

  /* Form styles */

  .donation-form {
    width: 500px;
    background-color: #fff;
    padding: 20px;
    border-radius: 10px;
  }

  .form-group {
    margin-bottom: 10px;
  }

  .form-label {
    display: block;
    margin-bottom: 5px;
  }

  .form-control {
    width: 100%;
    padding: 10px;
    border: 1px solid #ccc;
    border-radius: 5px;
  }

  .form-control:valid {
    border-color: green;
  }

  .form-select {
    width: 100%;
    padding: 10px;
    border: 1px solid #ccc;
    border-radius: 5px;
  }

  .form-btn {
    display: block;
    width: 100%;
    padding: 10px 20px;
    background-color: #007bff;
    color: #fff;
    border: none;
    border-radius: 5px;
    cursor: pointer;
  }

  @media (max-width: 576px) {
    .popup {
      width: 100%;
      max-width: unset;
    }
  }

.donation-form fieldset {
  border: 1px solid #ccc;
  border-radius: 5px;
  padding: 10px;
  margin-bottom: 20px;
}
  legend {
    font-size: 18px;
    font-weight: bold;
    padding: 5px;
    background-color: #f2f2f2;
    border: 1px solid #ccc;
    border-radius: 5px;
  }


  section {
    padding: 0 6em;
    overflow: hidden;
  }

  h2 {
    font-family: var(--paragraph-font);
    font-size: 3.5em;
    color: var(--justWhite);
  }

  p {
    font-family: var(--copy-font);
    font-size: 1em;
    color: var(--justWhite);
  }

  .yellow {
    color: var(--candelLight);
  }

  .page2-sponsor-page {
    height: max-content;
    width: 100%;
    padding-top: 7em;
    overflow-x: hidden;
  }

  .page2-sponsor-text {
    margin-bottom: 1em;
  }

  .page2-options-wrapper {
    position: relative;
    display: flex;
    flex-direction: row;
    height: 77%;
    width: 100%;
  }

  .page2-option {
    position: relative;
    height: 95%;
    width: 100%;
  }

  .page2-option1 svg {
    position: relative;
    fill: var(--candelLight);
  }

  .page2-option2 svg {
    fill: var(--pictonBlue);
  }

  .page2-option3 svg {
    fill: var(--jungleGreen);
  }

  .options-text-wrapper {
    position: absolute;
    top: 10%;
    left: 18%;
    width: 60%;
  }

  .black {
    color: var(--charcoal);
  }

  .page2-options-wrapper h3 {
    font-size: 2em;
    font-family: var(--paragraph-font);
    margin-bottom: 1em;
  }

  label {
  display: block;
  margin-bottom: 5px;
}

  @media (max-width: 768px) {
    /* Style for small screens (up to 768px) */

    section {
      padding: 0 2em;
    }

    h2 {
      font-size: 2.5em;
    }

    p {
      font-size: 0.8em;
    }

    .page2-sponsor-page {
      padding-top: 5em;
    }

    .page2-options-wrapper {
      height: 67%;
      flex-direction: column;
    }

    .options-text-wrapper {
      top: 10%;
      left: 10%;
      width: 80%;
    }
  }

  /* Media queries for small screens (up to 768px) */
@media (max-width: 768px) {
  section {
    padding: 0 2em;
  }

  h2 {
    font-size: 2.5em;
  }

  p {
    font-size: 0.8em;
  }

  .page2-sponsor-page {
    padding-top: 5em;
  }

  .page2-options-wrapper {
    height: 67%;
    flex-direction: column;
  }

  .options-text-wrapper {
    top: 10%;
    left: 10%;
    width: 80%;
  }
}
</style>
