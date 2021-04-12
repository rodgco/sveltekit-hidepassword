<script context="module">
  export async function load({ page }) {
    return {
      props: {
        user: {
          username: page.query.get("username"),
        },
      },
    };
  }
</script>

<script>
  export let user;
</script>

<h2>Welcome {user.username}!</h2>
