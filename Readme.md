# Frontend pull request checklist

_Or how to get looks-good-to-me on your pull request seven times faster_

This is a generalized version of a checklist, I’ve created for my colleagues at Wayfair. Feel free to fork it and adapt to your team’s needs.

## Before you start

1. Setup your environment to have immediate feedback on your changes:

   - [Setup ESLint plugin](https://eslint.org/docs/user-guide/integrations) in your editor.
   - [Setup Prettier plugin](https://prettier.io/docs/en/editors.html) in your editor.
   - [Setup TypeScript](https://www.typescriptlang.org/index.html#download-links) or Flow in your editor.
   - [Setup stylelint](https://stylelint.io/user-guide/complementary-tools#editor-plugins) in your editor.

2. Read your team’s coding standards and style guides.

## JavaScript

- JavaScript code is following team standards.

## HTML

- All code is [WCAG Level AA](https://www.w3.org/TR/2006/WD-WCAG20-20060427/appendixB.html) compliant.
  - _See [tools and techniques to use to test accessibility](https://daverupert.com/2018/07/assistive-technologies-i-test-with/)._
- Semantic tags are used where possible instead of `div`s and `span`s (headings, paragraphs, lists, etc.)
  - _See [Semantic HTML Tutorial](https://www.internetingishard.com/html-and-css/semantic-html/) for some examples._
- All interactive elements (links, buttons, form elements) are keyboard accessible and have visible focus states.
- Tab order of all interactive elements follows a logical pattern, usually their position on the screen and order in the DOM.
- All non-standard elements have appropriate ARIA roles.
- All interactive elements have accessible labels.
  - _For example, add accessible text using the VisuallyHidden component or something similar._
- All non-text content has a text alternative.
  - _For example, images have appropriate alt texts, clickable icons have titles, and videos have captions._
- UI looks good on any screen size (mobile, desktop, etc.).
- UI looks good with 200% page zoom.

## CSS

- CSS code is following team standards.
- No hardcoded colors, font sizes, whitespace, breakpoints and z-indices.
  - _Always use design tokens instead._
- No style overrides of any component library components.
- No unnecessary CSS, ideally there’s no CSS at all.
  - _For example, prefer to use primitive and layout components instead of custom styles._

## Tests

- Add tests for new functionality.
  - _For example, add unit tests for tricky code and regression tests for bugs._

## Documentation

- Document exposed API in a README or relevant documents.
- Use [ADR](https://github.com/joelparkerhenderson/architecture_decision_record) to keep track on architectural decisions.
- Use [UML diagrams](https://en.wikipedia.org/wiki/Unified_Modeling_Language) for complex flows.
  - _Hint: [PlantUML](https://plantuml.com/) can be a good starting point._

## Before sending code to review

- Read the ticket one more time and make sure everything is done as requested.
- Do a self review: carefully read all the code before opening a pull request. Think what kind of issues a reviewer may find in your code, what kind of questions they may have, what’s not clear. This alone can save you several review iterations and days in review.
  - _Having a coffee break or lunch before doing a self review could be a great idea to help you to look at your code with fresh eyes._
  - _Take notes, mental of physical, on what kind of comments you get in code reviews — you’ll notice that they are often repeated. You can save lots of time by making sure you won’t get any of the comments that you often receive._
  - _Hint: Use GUI Git clients for better experience like [GitHub Desktop](https://desktop.github.com/) or PhpStorm._
- No lint warnings, type errors or test failures.
  - _Hint: run these checks locally: `npm test`._
  - _Hint: many warnings can be autofixed, check the documentation for your ESLint plugin._
- No new errors and warning in the browser console.
- All code is formatted with Prettier.

## Pull request

- Add screenshots or GIFs for any UI changes. This will help the person reviewing your code to understand what you’ve changed and how it works.
  - _Hint: use [Kap](https://getkap.co/) or [Licecap](https://www.cockos.com/licecap/) to record your screen._
- If your team uses a particular template for pull requests, fill it. Otherwise at least make sure you have:
  - the user problem you are solving;
  - acceptance criteria of the ticket;
  - testing you have done or plan to do before release;
  - any pull request that are dependent on this one, or any tickets on which this pull request depends.

## Code review

- Ask to people to review your code:
  - a person who knows the domain well and can spot bugs in the business logic;
  - an expert in the technologies you’re using who can help you improve the code quality.
- When you’re done with the changes after a code review, do another self review of the code and write a comment to notify the reviewer, that the pull request is ready for another iteration.
- Review all the review comments and make sure they are all addressed before the next review iteration.
- Make sure you don’t have similar issues anywhere else in your pull request.
- If you’re not going to follow any of the code review recommendations, please add a comment explaining why.
- Avoid writing comment like "done" of "fixed" on each code review comment. Reviewers assume you’ll do all suggested changes, unless you have a reason not to do some of them.
- Sometimes it’s okay to postpone changes — in this case you’ll need to add a ticket number to the pull request and to the code itself.

## Asking help

- It’s okay if you don’t understand some of the code review comments. Don’t hesitate to ask questions in the pull request, or ping the reviewer directly.

## Resources

### Code reviews

- [How to get your code reviewed faster](https://blog.sapegin.me/all/faster-code-reviews)

### JavaScript

- [JavaScript for impatient programmers](http://exploringjs.com/impatient-js/)
- [Understanding ECMAScript 6](https://leanpub.com/understandinges6/)
- [Washing your code: write once, read seven times](https://leanpub.com/washingcode/)

### React

- [React docs](https://reactjs.org/docs/getting-started.html) (it’s one of the best resources)
- [The Beginner’s Guide to React](https://egghead.io/courses/the-beginner-s-guide-to-react)
- [Advanced React Component Patterns](https://egghead.io/courses/advanced-react-component-patterns)

### HTML

- [Semantic HTML](https://internetingishard.com/html-and-css/semantic-html/)

### CSS

- [How To Learn CSS](https://www.smashingmagazine.com/2019/01/how-to-learn-css/)

### Accessibility

- [A Short Guide to Screen Reader Friendly Code](https://benrobertson.io/accessibility/screen-reader-friendly-code-guide)
- [Accessible to all](https://web.dev/accessible)
- [Accessibility Tips for Web Developers](https://dev.to/addyosmani/accessibility-tips-for-web-developers-4cn0)
- [Assistive Technologies I Test With](https://daverupert.com/2018/07/assistive-technologies-i-test-with/)

### Testing

- [Modern React testing, part 1: best practices](https://blog.sapegin.me/all/react-testing-1-best-practices/)
- [What’s wrong with snapshot tests](https://blog.sapegin.me/all/snapshot-tests/)

---

## You may also like

- [Jest cheat sheet](https://github.com/sapegin/jest-cheat-sheet)
- [Opinionated list of React components](https://github.com/sapegin/react-components)

## Contributing

Improvements are welcome! Open an issue or send a pull request.

## Author and license

[Artem Sapegin](http://sapegin.me/), a frontend engineer at [Omio](https://omio.com/) and the creator of [React Styleguidist](https://react-styleguidist.js.org/). I also write about frontend at [my blog](https://blog.sapegin.me/).

CC0 1.0 Universal license, see the included [License.md](/License.md) file.
