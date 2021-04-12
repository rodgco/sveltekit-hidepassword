<script>
  import PasswordShowHide from "$lib/PasswordShowHide.svelte";
</script>

<form action="/welcome" method="GET">
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
  form {
    flex: 1 0 auto;
    overflow: hidden;
    width: 100%;
    max-width: 20em;
    background: #def;
    border-radius: 0.5em;
    box-shadow: 0.1em 0.25em 0.5em #0004;
  }
  form h2 {
    padding: 0.4em 0.8em;
    font-size: 1.25em;
    background: #048;
    color: #fff;
  }
  form fieldset {
    padding: 1em;
    border: none;
  }
  form label {
    display: block;
    padding-bottom: 1em;
  }
  form input {
    box-sizing: border-box;
    float: left;
    width: 100%;
    padding: 0.25em 0.5em;
    margin: 0.25em 0 1em;
    border: 1px solid #5af;
    border-radius: 0.25em;
  }
  form .submitsAndHiddens {
    padding: 0 1em;
  }
  form .submitsAndHiddens button {
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
  form .submitsAndHiddens button:focus,
  form .submitsAndHiddens button:hover {
    background: #8bf;
  }
  form p {
    clear: both;
    text-align: center;
    padding: 1em 0;
  }
</style>
