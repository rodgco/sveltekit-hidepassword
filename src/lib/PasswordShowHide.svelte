<script>
  import { onMount } from "svelte";

  let showPassword = false;
  let passwordInput;

  let jsEnabled = false;

  onMount(() => {
    jsEnabled = true;
  });

  function passwordShowHide(event) {
    showPassword = !showPassword;
    passwordInput.focus();
  }
</script>

<input
  type={showPassword ? "text" : "password"}
  name="password"
  bind:this={passwordInput}
  required
/>
{#if jsEnabled}
  <button title="Show / Hide Password" type="button" on:click={passwordShowHide}
    >👁</button
  >
{/if}

<style>
  input {
    box-sizing: border-box;
    float: left;
    width: 100%;
    padding: 0.25em 0.5em;
    margin: 0.25em 0 1em;
    border: 1px solid #5af;
    border-radius: 0.25em;
  }
  button {
    position: relative;
    float: left;
    width: 1.6em;
    margin-left: -1.6em;
    padding: 0.45em 0;
    font-size: 1.25em;
    line-height: 1.2em;
    text-align: center;
    border: none;
    background: transparent;
    transition: transform 0.3s;
    transform-origin: center;
  }
  button:focus {
    outline: none;
    font-weight: bold;
    text-shadow: 0 0 0.2em #5af;
  }
  button:hover {
    transform: scale(1.5);
  }
  input[type="text"] + button:after {
    content: "\2215";
    position: absolute;
    left: 0;
    top: 0.45em;
    width: 1.6em;
    text-align: center;
    text-shadow: -0.1em 0 0 #fff, 0.1em 0 0 #fff;
    color: #f00;
  }
</style>
