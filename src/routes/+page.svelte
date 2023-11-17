<script>
    import Header from "$lib/components/Header.svelte";
    import Footer from "$lib/components/Footer.svelte";
    import { onMount } from 'svelte';

    // export let data
    // console.log(data.sponsorPages)

    let showPopup = false;

onMount(() => {
  const donateButton = document.querySelector('#donate-button');

  donateButton.addEventListener('click', () => {
    showPopup = true;
  });
});

function closePopup() {
  showPopup = false;
}

</script>

<Header />


<main>

    <section class="page2-sponsor-page">
        <div class="text-area">
            <h2 class="page2-numbers-header page2-sponsor-text">Become a <span class="yellow">sponsor</span></h2>
        </div>
        <div class="page2-options-wrapper">
            <div class="page2-option page2-option1">
                <svg viewBox="0 0 149 198" fill="none" xmlns="http://www.w3.org/2000/svg">
                    <path
                        d="M142.515 0.00614879C149.727 0.0915737 149.942 0.333528 147.852 22.5583C143.991 63.6479 139.988 104.595 136.045 145.599C134.83 158.214 133.616 170.828 132.406 183.457C131.2 195.986 130.626 197.808 126.631 197.894C116.059 198.093 105.483 197.951 94.9109 197.951L64.907 197.951L64.907 197.979C45.1876 197.979 25.4724 198.008 5.753 197.965C-0.75149 197.965 -0.93599 196.897 1.26936 176.281C6.61111 126.307 11.9443 76.3336 17.226 26.3029C18.2814 16.2797 20.002 10.1005 23.4258 10.4992C24.846 10.67 26.2748 9.8728 27.7035 9.77314C51.4132 8.13582 75.1228 6.0998 98.8325 5.1174C113.412 4.50519 127.935 -0.193176 142.515 0.00614879Z"
                        fill="" />
                </svg>
                <div class="options-text-wrapper">
                    <h3 class="black">Option 1</h3>
                    <p class="black">Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor
                        incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation
                        ullamco laboris</p>
                        <button id="donate-button" on:click={() => showPopup = true}>Donate</button>
                </div>
            </div>
            <div class="page2-option page2-option2">
                <svg viewBox="0 0 149 198" fill="none" xmlns="http://www.w3.org/2000/svg">
                    <path
                        d="M142.515 0.00614879C149.727 0.0915737 149.942 0.333528 147.852 22.5583C143.991 63.6479 139.988 104.595 136.045 145.599C134.83 158.214 133.616 170.828 132.406 183.457C131.2 195.986 130.626 197.808 126.631 197.894C116.059 198.093 105.483 197.951 94.9109 197.951L64.907 197.951L64.907 197.979C45.1876 197.979 25.4724 198.008 5.753 197.965C-0.75149 197.965 -0.93599 196.897 1.26936 176.281C6.61111 126.307 11.9443 76.3336 17.226 26.3029C18.2814 16.2797 20.002 10.1005 23.4258 10.4992C24.846 10.67 26.2748 9.8728 27.7035 9.77314C51.4132 8.13582 75.1228 6.0998 98.8325 5.1174C113.412 4.50519 127.935 -0.193176 142.515 0.00614879Z"
                        fill="" />
                </svg>
                <div class="options-text-wrapper">
                    <h3>Option 2</h3>

                    <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut
                        labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco
                        laboris</p>

                        <button id="donate-button" on:click={() => showPopup = true}>Donate</button>
                </div>
            </div>
            <div class="page2-option page2-option3">
                <svg viewBox="0 0 149 198" fill="none" xmlns="http://www.w3.org/2000/svg">
                    <path
                        d="M142.515 0.00614879C149.727 0.0915737 149.942 0.333528 147.852 22.5583C143.991 63.6479 139.988 104.595 136.045 145.599C134.83 158.214 133.616 170.828 132.406 183.457C131.2 195.986 130.626 197.808 126.631 197.894C116.059 198.093 105.483 197.951 94.9109 197.951L64.907 197.951L64.907 197.979C45.1876 197.979 25.4724 198.008 5.753 197.965C-0.75149 197.965 -0.93599 196.897 1.26936 176.281C6.61111 126.307 11.9443 76.3336 17.226 26.3029C18.2814 16.2797 20.002 10.1005 23.4258 10.4992C24.846 10.67 26.2748 9.8728 27.7035 9.77314C51.4132 8.13582 75.1228 6.0998 98.8325 5.1174C113.412 4.50519 127.935 -0.193176 142.515 0.00614879Z"
                        fill="" />
                </svg>
                <div class="options-text-wrapper">
                    <h3>Option 3</h3>
                    <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut
                        labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco
                        laboris</p>
                        <button id="donate-button" on:click={() => showPopup = true}>Donate</button>
                </div>
            </div>
        </div>
    </section>

    {#if showPopup}
  <div class="popup">
    <h2>Sponsor Donation</h2>
    <p>Please enter your credit card information to make a donation.</p>

    <form>
      <label for="name">Name:</label>
      <input type="text" id="name" required>

      <label for="creditCardNumber">Credit Card Number:</label>
      <input type="number" id="creditCardNumber" required>

      <label for="expirationDate">Expiration Date:</label>
      <input type="date" id="expirationDate" required>

      <label for="cvv">CVV:</label>
      <input type="number" id="cvv" required>

      <label for="option">Select an option:</label>
      <select id="option" required>
        <option value="1">1</option>
        <option value="2">2</option>
        <option value="3">3</option>
      </select>

      <label for="dollar">How much $:</label>
      <input type="number" id="dollar" required pattern="[0-9.]+$">

      <button type="submit">Donate</button>
    </form>

    <button on:click={closePopup}>Close</button>
  </div>
{/if}

</main>

<Footer />

<style>
.popup {
  position: fixed;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  max-width: 400px;
  background-color: var(--jungleGreen);
  padding: 20px;
  border-radius: 10px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
}

@media (max-width: 576px) {
  .popup {
    width: 100%;
    max-width: unset;
  }
}

.popup h2 {
  text-align: center;
  color: var(--candelLight);
  font-size: 24px;
  font-weight: bold;
  margin-bottom: 20px;
}

.popup form {
  display: flex;
  color: var(--candelLight);
  flex-direction: column;
  margin-bottom: 20px;
}

.popup label {
  display: block;
  font-size: 16px;
  color: var(--candelLight);
  margin-bottom: 5px;
}

.popup input {
  width: 100%;
  padding: 5px;
  border: none;
  border-radius: 5px;
  box-shadow: 0 0 5px rgba(0, 0, 0, 0.1);
}

.popup button {
  padding: 5px 10px;
  border: none;
  border-radius: 5px;
  background-color: #007bff;
  color: #fff;
  margin-bottom: 15px;
  cursor: pointer;
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

#donate-button {
    background-color: #0055B8;
    color: #fff;
    padding: 10px 20px;
    border: none;
    border-radius: 30px;
    font-size: 16px;
    font-weight: bold;
    cursor: pointer;
}

#donate-button:hover {
    background-color: #0069d9;
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

</style>