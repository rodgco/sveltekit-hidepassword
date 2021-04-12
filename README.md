# HTML / CSS / JavaScript Password Show and Hide

I've just recently got to know about Jason Knight's posts on Medium, and I agree with his point of view on the semantic web, the separation of concerns between HTML and CSS.

I'm taking some of his ideas and adapting them to Svelte Kit, and learn something along the way, specially around A11y.

For this first experiment with his ideas I've taken his view on [HTML / CSS / JavaScript Password Show and Hide](https://levelup.gitconnected.com/html-css-javascript-password-show-and-hide-7c3e3a473baf). It's an interesting approach to implement show / hide functionality to password inputs.

## The HTML & CSS

As I'm using Svelte Kit, the first thing I did was how to separate the content into the different parts of Svelte Kit.

I identified three code blocks...

- A reset system that makes sense to be implemented in `src/app.css`
- The page boilerplate with `header`, `main` and `footer`, that ended up in `src/routes/$layout` with the respective CSS.
- The main content was placed on `src/routes/index.svelte`, with the respective CSS and JS.
- The password input with its structure, presentation and login placed on a component in `src/lib/PasswordShowHide.svelte`.

### src/app.css

As Svelte Kit mount in `<div id="svelte">%svelte.body%</div>` changed the `body` CSS to `#svelte`, so the flex parameters would behave as expected.

### src/routes/$layout

Pretty straightforward, all the boilerplate with the expected `<slot />` nested on the `<main>` tag. All the respective CSS also moved in here.

### src/routes/index.svelte

Here I decided to use a little bit of Svelte Magic and separate the concerns a little bit, so I kept all the form boilerplate with the respective CSS, and moved all the password input into a separate component.

One important lesson I've learned was the use of coments to help me with the code. I usually struggle to programatically get rid of all vscode warnings, and there was the legitimate complain that "A11y: A form label must be associated with a control", my first tought was to move the `<label>` within the newly created component, but that would narrow the use cases and bloat the component. So i decided to ignore the message with `<!-- svelte-ignore a11y-label-has-associated-control -->`, and I'm fine with that.

### src/lib/PasswordShowHide.svelte

Now, if you want to see magic, here it is...

Comparing the bloated JS of Jason's post this is much cleaner and friendly.

- The show hide button is described in the HTML, no need to insert it via code.
- Changing the state is simpler, managed by a boolean variable. No need to change the DOM directly.
- As Svelte scope the CSS, it got simpler, with direct and clear references.

## Conclusion

I'm not an expert on many frameworks, all I can say is that I'm more than satisfied with the Developer Experience delivered by Svelte. In the same manner it delivered a consistent and cohesive sepration of structure and presentation, as expected by the original author.

Update: Got feedback from the author and got his points, specially regarding degradation for non-js enabled browsers. Changed the PasswordShowHide component to handle that and implemented better form handling.

You can see a runing version at (https://sveltekit-hidepassword.vercel.app/).
