---
title: Key Differences
---

<Alert type="info">

## <Icon name="graduation-cap"></Icon> What you'll learn

- What makes Cypress unique
- How its architecture differs from Selenium
- New testing approaches not possible before

</Alert>

## Architecture

Most testing tools (like Selenium) operate by running outside of the browser and
executing remote commands across the network. _Cypress is the exact opposite._
Cypress is executed in the same run loop as your application.

Behind Cypress is a Node server process. Cypress and the Node process constantly
communicate, synchronize, and perform tasks on behalf of each other. Having
access to both parts (front and back) gives us the ability to respond to your
application's events in real time, while at the same time work outside of the
browser for tasks that require a higher privilege.

Cypress also operates at the network layer by reading and altering web traffic
on the fly. This enables Cypress to not only modify everything coming in and out
of the browser, but also to change code that may interfere with its ability to
automate the browser.

Cypress ultimately controls the entire automation process from top to bottom,
which puts it in the unique position of being able to understand everything
happening in and outside of the browser. This means Cypress is capable of
delivering more consistent results than any other testing tool.

Because Cypress is
[installed locally](/guides/getting-started/installing-cypress) on your machine,
it can additionally tap into the operating system for automation tasks. This
makes performing tasks such as
[taking screenshots, recording videos](/guides/guides/screenshots-and-videos),
general [file system operations](/api/commands/exec) and
[network operations](/api/commands/request) possible.

## Native access

Because Cypress operates within your application, that means it has native
access to every single object. Whether it is the `window`, the `document`, a DOM
element, your application instance, a function, a timer, a service worker, or
anything else - you have access to it in your Cypress tests. There is no object
serialization, there is no over-the-wire protocol - you have access to
everything. Your test code can access all the same objects that your application
code can.

## New kind of testing

Having ultimate control over your application, the network traffic, and native
access to every host object unlocks a new way of testing that has never been
possible before. Instead of being 'locked out' of your application and not being
able to easily control it - Cypress instead lets you alter any aspect of how
your application works. Instead of slow and expensive tests, such as creating
the state required for a given situation, you can create these states
artificially like you would in an unit test. For instance you can:

- [Stub](/api/commands/stub) the browser or your application's functions and
  force them to behave as needed in your test case.
- Expose data stores (like in Redux) so you can programmatically alter the state
  of your application directly from your test code.
- Test edge cases like 'empty views' by forcing your server to send empty
  responses.
- Test how your application responds to errors on your server by modifying
  response status codes to be 500.
- Modify DOM elements directly - like forcing hidden elements to be shown.
- Use 3rd party plugins programmatically. Instead of fussing with complex UI
  widgets like multi selects, autocompletes, drop downs, tree views or
  calendars, you can call methods directly from your test code to control them.
- [Prevent Google Analytics from loading _before_ any of your application code executes](/guides/references/configuration#blockHosts)
  when testing.
- Get synchronous notifications whenever your application transitions to a new
  page or when it begins to unload.
- [Control time by moving forward or backward](/api/commands/clock) so that
  timers or polls automatically fire without having to wait for the required
  time in your tests.
- Add your own event listeners to respond to your application. You could update
  your application code to behave differently when under tests in Cypress. You
  can control WebSocket messages from within Cypress, conditionally load 3rd
  party scripts, or call functions directly on your application.

## Shortcuts

Trying to test hard to reach areas of your application? Don't like the side
effects an action creates? Tired of repeating the same repetitive and slow
actions over and over again? You can skip them for most test cases.

Cypress allows for browser context to be cached with
[`cy.session()`](/api/commands/session). This means as a user, you only need to
perform authentication once for the entirety of your test suite, and restore the
saved session between each test. That means you do not have to visit a login
page, type in a username and password and wait for the page to load and/or
redirect for every test you run. You can accomplish this once with
[`cy.session()`](/api/commands/session) and if needed,
[`cy.origin()`](/api/commands/origin).

Cypress also gives you the ability to take shortcuts and programmatically log
in. With commands like [`cy.request()`](/api/commands/request), you can send
HTTP requests directly, yet have those requests synchronized with the browser.
Cookies are automatically sent and applied back. Worried about CORS? Don't be,
it is completely bypassed. The power to choose when to test like a user and when
to skip slow and repetitive parts is yours.

## Flake resistant

Cypress knows and understands everything that happens in your application
synchronously. It is notified the moment the page loads and the moment the page
unloads. It is impossible for Cypress to miss elements when it fires events.
Cypress even knows how fast an element is animating and will
[wait for it to stop animating](/guides/core-concepts/interacting-with-elements#Animations).
Additionally, it
[automatically waits for elements to become visible](/guides/core-concepts/interacting-with-elements#Visibility),
to [become enabled](/guides/core-concepts/interacting-with-elements#Disability),
and to
[stop being covered](/guides/core-concepts/interacting-with-elements#Covering).
When pages begin to transition, Cypress will pause command execution until the
following page is fully loaded. You can even tell Cypress to
[wait](/api/commands/wait) on specific network requests to finish.

Cypress executes the vast majority of its commands inside the browser, so there
is no network lag. Commands execute and drive your application as fast as it is
capable of rendering. To deal with modern JavaScript frameworks with complex
UIs, you use assertions to tell Cypress what the desired state of your
application should be. Cypress will automatically wait for your application to
reach this state before moving on. You are completely insulated from fussing
with manual waits or retries. Cypress automatically waits for elements to exist
and will never yield you stale elements that have been detached from the DOM.

## Debuggability

Above all else Cypress has been built for usability.

There are hundreds of custom error messages describing the exact reason Cypress
failed your test.

There is a rich UI which visually shows you the command execution, assertions,
network requests, spies, stubs, page loads, or URL changes.

Cypress takes snapshots of your application and enables you to time travel back
to the state it was in when commands ran.

You can use the Developer Tools while your tests run, you can see every console
message, every network request. You can inspect elements, and you can even use
debugger statements in your spec code or your application code. There is no
fidelity loss - you can use all the tools you're already comfortable with. This
enables you to test and develop all at the same time.

## Trade offs

While there are many new and powerful capabilities of Cypress - there are also
important trade-offs that we've made in making this possible.

If you're interested in understanding more, we've written
[an entire guide](/guides/references/trade-offs) on this topic.
