---
id: 6144e818fd5ea704fe56081d
title: Step 28
challengeType: 0
dashedName: step-28
---

# --description--

Give each `fieldset` an adaquate `name` attribute. Then, give both unordered lists a `class` of `answers-list`.

Finally, use the `legend` to caption the content of the `fieldset` by placing a true/false question as the text content.

# --hints--

You should give the first `fieldset` an adaquate `name` attribute. _Hint: I would use `html-question-one`_

```js
assert.notEmpty(document.querySelectorAll('fieldset')?.[0]?.name);
```

You should give the second `fieldset` an adaquate `name` attribute. _Hint: I would use `html-question-two`_

```js
assert.notEmpty(document.querySelectorAll('fieldset')?.[1]?.name);
```

You should give the first `ul` element a `class` of `answers-list`.

```js
assert.equal(document.querySelectorAll('fieldset > ul')?.[0]?.className, 'answers-list');
```

You should give the second `ul` element a `class` of `answers-list`.

```js
assert.equal(document.querySelectorAll('fieldset > ul')?.[1]?.className, 'answers-list');
```

You should give the first `legend` element text content.

```js
assert.notEmpty(document.querySelectorAll('legend')?.[0]?.textContent);
```

You should give the second `legend` element text content.

```js
assert.notEmpty(document.querySelectorAll('legend')?.[1]?.textContent);
```

You should not use the same text content for both `legend` elements.

```js
assert.notEqual(document.querySelectorAll('legend')?.[0]?.textContent, document.querySelectorAll('legend')?.[1]?.textContent);
```

# --seed--

## --seed-contents--

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <meta name="description" content="freeCodeCamp Accessibility Quiz practice project" />
    <title>freeCodeCamp: Accessibility Quiz</title>
    <link rel="stylesheet" href="styles.css" />
  </head>
  <body>
    <header>
      <img id="logo" src="https://cdn.freecodecamp.org/platform/universal/fcc_primary.svg">
      <h1>HTML/CSS Quiz</h1>
      <nav>
        <ul>
          <li><a href="#student-info">INFO</a></li>
          <li><a href="#html-questions">HTML</a></li>
          <li><a href="#css-questions">CSS</a></li>
			  </ul>
      </nav>
    </header>
    <main>
      <form method="post" action="https://freecodecamp.org/practice-project/accessibility-quiz">
        <section role="region" aria-labelledby="student-info">
          <h2 id="student-info">Student Info</h2>
          <div class="info">
            <label for="student-name">Name:</label>
            <input type="text" name="student-name" id="student-name" />
          </div>
          <div class="info">
            <label for="student-email">Email:</label>
            <input type="email" name="student-email" id="student-email" />
          </div>
          <div class="info">
            <label for="birth-date">D.O.B.<span class="sr-only">(Date of Birth)</span></label>
            <input type="date" name="birth-date" id="birth-date" />
          </div>
        </section>
--fcc-editable-region--
        <section role="region" aria-labelledby="html-questions">
          <h2 id="html-questions">HTML</h2>
          <div class="question-block">
            <p>1</p>
            <fieldset class="question">
              <legend></legend>
              <ul>
                <li></li>
                <li></li>
              </ul>
            </fieldset>
          </div>
          <div class="question-block">
            <p>2</p>
            <fieldset class="question">
              <legend></legend>
              <ul>
                <li></li>
                <li></li>
              </ul>
            </fieldset>
          </div>
        </section>
--fcc-editable-region--
        <section role="region" aria-labelledby="css-questions">
          <h2 id="css-questions">CSS</h2>
        </section>
      </form>
    </main>
  </body>
</html>

```

```css
body {
  background: #f5f6f7;
	color: #1b1b32;
	font-family: Helvetica;
	margin: 0;
}

header {
  width: 100%;
	height: 50px;
	background-color: #1b1b32;
	display: flex;
}

#logo {
  width: max(100px, 18vw);
	background-color: #0a0a23;
  aspect-ratio: 35 / 4;
	padding: 0.4rem;
}

h1 {
  color: #f1be32;
	font-size: min(5vw, 1.2em);
}

nav {
  width: 50%;
	max-width: 300px;
	height: 50px;
}

nav > ul {
  display: flex;
	justify-content: space-evenly;
}

h1,
h2 {
  font-family: Verdana, Tahoma;
}

h2 {
  border-bottom: 4px solid #dfdfe2;
}

.sr-only {
	position: absolute;
	width: 1px;
	height: 1px;
	padding: 0;
	margin: -1px;
	overflow: hidden;
	clip: rect(0, 0, 0, 0);
	white-space: nowrap;
	border: 0;
}

```