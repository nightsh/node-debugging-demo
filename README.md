# Intro

Hi, this is a small demo repo to go through a few simple node debugging
techniques and tips.

It's nothing more than a small "Hello world" Express application, handling a we
request, catching it in a route, then bouncing it back to the client together
with a "Hello world" body.

# Debugging intro

I'll start by pointing out a 
[blog post](https://umbra.xyz/debugging-node-js-a-quick-intro/) 
I made not long ago on the subject, containing screenshots and small useful
samples. The examples in the post are slightly different and therefore we might see
some differences in the tools used. So mix and match, people! :-)

## `npm` scripts

* `start` runs the app
* `debug` runs the app, opening up a debugger connection
* `inspect` runs the app, opening up a debugger connection accesible through
  the [Chrome node debugger](https://umbra.xyz/content/images/2017/02/Spectacle.M20323.png)

## Getting ready

Place a `debugger;` statement aywhere in the code, where you'd like to have a
breakpoint. That's when code execution will freeze, waiting for your
intervention, then resume when you allow it to continue.

### Simple `--debug` flag

This one opens a port (usually `5858`) that can be accessed through the node
debugger. Just run `npm run debug`, then in another terminal window run `node
debug localhost:5858`.

This takes you into a debugger command line interface. Probably the most useful
thing you'd want to do is type `repl` and hit Enter. This takes you to the
breakpoint's location and context are you'll be able to sniff around potential
issues **without relying on `console.log()` commands** or similar.

Alternatively, type `help` and Enter, and see a list of commands available
there.

### `--inspect`

This is a more common way to debug complex apps, due to its convenience of
living inside a web browser. When you have a bunch of big objects, the
expand/collapse controls of the Chrome Dev Tools will do you a lot of good, as
opposed to doing a request dump in the terminal and scroll through it.

You can [refer to the blog post section #2](https://umbra.xyz/debugging-node-js-a-quick-intro/) 
for a written walkthrough.

## Notes

* don't forget to `.gitignore` your `npm-debug.log` file!
* make sure you have node debugging enabled in browser
* make sure your ports are free and accessible (firewalls might overdo it
  sometimes)
* last but not least, choose your breakpoint(s) location(s) wisely ;-)

# License of this repo

...is [WTFPL](http://www.wtfpl.net/).
