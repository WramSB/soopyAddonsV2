## soopyAddonsV2
#About
ChatTriggers is a framework for Minecraft that allows for live scripting and client modification using JavaScript. We provide libraries, wrappers, objects and more to make your life as a modder as easy as possible. Even without the proper wrapper, you can still use exposed Minecraft methods and variables but you will need knowledge of FML mappings. The entire ChatTriggers engine is built on Rhino using Java 8 so you have access to any Rhino methods and functions. Rhino supports some ES6 features, as can be seen here.

The basic premise of ChatTriggers is that everything is based around Triggers. From a modding standpoint, Triggers can be thought of as event listeners. These can range from a chat Trigger that runs on a specific chat event matching criteria to a render overlay Trigger that runs when the crosshair is being rendered. We are constantly adding more Triggers and Trigger types as the mod evolves for more integration with Minecraft.

register("chat", function(name, message, event) {
  cancel(event);
  ChatLib.chat(name + ": " + message);
}).setCriteria("<${name}> ${message}");

register("renderCrosshair", function(event) {
  cancel(event);
  Renderer.drawRect(
    0x50ffffff,
    Renderer.screen.getWidth() / 2 - 1,
    Renderer.screen.getHeight() / 2 - 1,
    2, 2
  );
});
You can learn the basics of scripting with ChatTriggers from the Slate tutorial and once you get the basics, check out the JavaDocs for a more in depth look at all of the available methods.

#Releases
The ChatTriggers website will always be kept up to date with the latest release. As of beta version 0.6.4, we have started to move the release changelog along with a .jar download (mirror of the website) to the GitHub releases page.

#Feature changes
Any major features are moved to separate branches before being merged into master. This will avoid the issue of waiting after a release to fix bugs when we want to be working on new features. Any contributors will have to abide by the same standard. New features get their own branch and bug fixes require a pull request on the master branch.

#Issues
Any issue can be opened using the normal GitHub issue page. Issues can be anything from bug reports to feature requests. For us to consider an issue to be valid, it needs a simple but effective title that conveys the problem in a few words and a well thought out and well written description.

#Bug Report
Should be reproducible
Needs a step by step guide on how to reproduce
Any evidence of the bug occurring (e.g. images or video) is welcome
Feature Request
Needs a general description of the feature requests
Specifics on what is being requested (e.g. what class you want it in or what it should do) is highly recommended
Duplicate issues will be merged to avoid too much clutter. If an issue is moved to "next" we will usually comment on it to explain how we expect to implement or fix that issue.
