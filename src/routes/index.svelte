<script>
  import PasswordShowHide from "$lib/PasswordShowHide.svelte";

  function handleForm(e) {
    console.log(e);
    console.log("Username:", e.target.elements.username.value);
    console.log("Password:", e.target.elements.password.value);
  }
</script>

<form action="#" method="GET" id="login" on:submit|preventDefault={handleForm}>
  <h2>Login</h2>
  <fieldset>
    <label>
      Username:<br />
      <input type="text" name="username" required /><br />
    </label>
    <!-- svelte-ignore a11y-label-has-associated-control -->
    <label>
      Password:<br />
      <PasswordShowHide /><br />
    </label>
  </fieldset>
  <div class="submitsAndHiddens">
    <button>Submit</button>
    <a href="/forgot">Forgot Password?</a>
    <p>
      If you do not have an existing account,
      <a href="/signup">Register Now!</a>
    </p>
  </div>
</form>

<style>
  #login {
    flex: 1 0 auto;
    overflow: hidden;
    width: 100%;
    max-width: 20em;
    background: #def;
    border-radius: 0.5em;
    box-shadow: 0.1em 0.25em 0.5em #0004;
  }
  #login h2 {
    padding: 0.4em 0.8em;
    font-size: 1.25em;
    background: #048;
    color: #fff;
  }
  #login fieldset {
    padding: 1em;
    border: none;
  }
  #login label {
    display: block;
    padding-bottom: 1em;
  }
  #login input {
    box-sizing: border-box;
    float: left;
    width: 100%;
    padding: 0.25em 0.5em;
    margin: 0.25em 0 1em;
    border: 1px solid #5af;
    border-radius: 0.25em;
  }
  #login .submitsAndHiddens {
    padding: 0 1em;
  }
  #login .submitsAndHiddens button {
    float: right;
    box-sizing: border-box;
    padding: 0.25em 1em;
    margin-top: -0.25em;
    background: #ace;
    border: 1px solid #5af;
    border-radius: 0.25em;
    box-shadow: inset 0 1em 1em #fff8;
    transition: background 0.3s;
  }
  #login .submitsAndHiddens button:focus,
  #login .submitsAndHiddens button:hover {
    background: #8bf;
  }
  #login p {
    clear: both;
    text-align: center;
    padding: 1em 0;
  }
</style>
