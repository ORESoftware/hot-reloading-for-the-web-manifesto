# Hot Reloading for the Web, A Manifesto



## Abstract

Hot-reloading, more generally hot-loading (HL) is the concept of loading new code into a runtime, in realtime. 
This can be done to various effect in all sorts of programs for different purposes. Hot reloading is a goal of UI development,
so that both visual design and rendering logic can be changed rapidly. This will lead to faster development iteration on the part of individual developers,
on a minute-by-minute basis. Unfortunately, despite the advantageous promised by hot-reloading, it is not a facility
that is well-known or understood by most web developers. Good extended experience with hot-reloading systems is rare, both inside and outside of web development.

Experience with hot-reloading of code is shared by developers in the following
areas: (Talk about Erlang, JRebel, process-per-request systems like PHP, and any front-end web development systems that had such a thing).
 
* If you have had a positive experience with a hot-reloading web-front-end workflow, please feel free to modify the HL-stories.md file with a PR,
 and add your info to the list of successful/not-so-successful hot-reloading systems.
 
Unfortunately, with the modern web front-end changing so often, hot-reloading has been again relegated as a lower-priority feature.
As authors of this manifesto we feel that hot-reloading is an underrated feature for front-end web development and should be
a higher priority.


## Hot Reloading As We Envision It

### Here are the requirements of a modern web-front-end hot-reloading system:


1. Does not require a page refresh; this is obvious for those familiar with HL;
developers should be able to make changes to their codebase and see the changes
reflected in the UI immediately. By eschewing a refresh, we preserve console logging
output, which aids developers.

2. Can hot-reload CSS, JS and HTML alike.

3. Loads new code into the runtime (HTML, CSS, JS) without any changes to state in JavaScript - the code changes;
the data should not change.

4. Maximize the amount of the codebase that can be hot-reloaded, so as to minimize the amount of information the developer
has to hold in their head as to what can and cannot be hot-reloaded.

5. Works in a predictable, consistent manner, without any real contingincies or bugs.

6. Requires minimal if not zero onus on the front-end developer to adhere to certain coding patterns or constraints;
that is to say - hot-reloading features should work with near zero-configuration and constraints on the front-end.

7. 
  7a. Cross-IDE: Can work across different IDE's; that is, backend support for hot-reloading (most likely websockets)
should be IDE agnostic.

  7b. Cross-platform - Should be platform independent - support for Windows and *nix (where MacOS is a *nix flavor).

  7c. Cross-browser - Can work in all browsers; that is to say it is browser independent.

8. 
  8a. Requires minimum server-side configuration to enable front-end hot-reloading. Hot reloading should be easy to
"turn on" and "turn off" on the part of the developer.

  8b. Hot-reloading should be available in "development mode", but safely disabled by default in "production mode".


9. Clear visual feedback

  9a. Clear visual feedback that the reload was successful.
  9b. Clear visual feedback if there is an error.
      
10. Front-end should be able to recover from runtime errors, that occur upon a reload, gracefully and without any 
subsequent page refresh. To be precise, if the developer loads new code and it causes a runtime error, 
they should be able to see the error trace on the 
screen in the web portal, fix the mistake in their codebase, and then re-reload the new code and the runtime, if error
free, should be able to be back to normal with the new updates.