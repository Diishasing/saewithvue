<template>
  <div id="form-wrapper">
    <div class="some-headings">
      <h3 id="query-line">Any Query?</h3>
    </div>
    <div id="form-container">
      <form action="https://formspree.io/mvogvvgj" method="POST">
        <div>
          <label for="message">Query :</label>
          <textarea
            name="message"
            id="message"
            placeholder="Message"
            minlength="1"
            rows="4"
            oninvalid="this.setCustomValidity('Please Enter Your question.')"
            oninput="setCustomValidity('')"
            required
          ></textarea>
        </div>
        <div>
          <label for="name">Name :</label>
          <input
            type="text"
            id="name"
            name="name"
            minlength="1"
            placeholder="Your name"
            oninvalid="this.setCustomValidity('Please Enter Your Name')"
            oninput="setCustomValidity('')"
            required
          />
        </div>
        <div>
          <label for="email">Email :</label>
          <input
            type="email"
            id="email"
            name="email"
            placeholder="Enter your Email-ID"
            oninvalid="this.setCustomValidity('Please provide valid email')"
            oninput="setCustomValidity('')"
            required
          />
        </div>
        <div id="button-setter">
          <button type="submit">
            Send Query
            <img
              :src="
                require('@/assets/icons/home_icons/chevron-solid-white.svg')
              "
              class="chevron-solid"
              alt="submit the form"
            />
          </button>
        </div>
      </form>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style scoped>
form button {
  background-color: #414141;
  color: white;
  padding: 12px;
  border: none;
  outline: none;
}
form button:hover {
  cursor: pointer;
  background-color: #2c2c2c;
}
.some-headings {
  text-align: center;
  font: 600 2.59em Domine;
  padding: 30px 5%;
}
#form-wrapper {
  overflow: hidden;
  padding: 50px 0;
  border-top: 2px solid goldenrod;
  background: linear-gradient(
    45deg,
    rgba(255, 129, 12, 0.712),
    rgba(253, 96, 82, 0.801)
  );
}
#button-setter {
  font-family: "Open Sans";
  width: fit-content;
  margin: auto;
  padding: 0;
  border-radius: 300px;
  overflow: hidden;
}
#form-wrapper:hover #query-line {
  transform: translateY(-10px) scale(1.4);
  transition: 0.3s transform linear;
}

#form-container {
  min-height: 200px;
  width: fit-content;
  margin: auto;
  padding: 12px;
}

#query-line {
  border-bottom: 2px solid black;
  transition: transform 300ms;
}

form {
  width: fit-content;
  margin: auto;
}

form > div {
  padding: 5% 0;
}
label {
  font-weight: 600;
}
form input {
  padding: 5%;
  width: 100%;
}
textarea {
  width: 100%;
  padding: 5%;
}
</style>
