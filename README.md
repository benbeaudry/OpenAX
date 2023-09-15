# Accessibility Innovations
Author: Benjamin Beaudry  
Last updated: 9/15/2023

## Abstract
The web platform evolves at an unparalleled rate, largely propelled by the extensive resources provided to web developers to innovate and compete. The same catalyst for innovation — technologies that empower developers — is noticeably absent when it comes to accessibility. A complex approval process, limited Application Programming Interfaces (APIs), and an outdated focus on graphical user interfaces create significant roadblocks. This stagnation doesn't just affect those with disabilities; it risks widening societal divides, making it a pressing issue that requires immediate attention.

In this paper, I argue for a revitalized approach to accessibility and present a multifaceted strategy to tackle existing challenges. It emphasizes the need to simplify the bureaucratic procedures for approval, develop APIs with greater adaptability, and redefine how assistive tools engage with different types of user interfaces. By addressing these core issues, we can accelerate the pace of innovation and craft more effective web accessibility solutions.

This paper underscores the immediate need for collective action among industry stakeholders. By jointly addressing the highlighted issues, we have a unique opportunity to stimulate innovation and make the web a genuinely accessible and empowering platform for everyone.

>In my role as an engineer focused on the accessibility platforms for Microsoft Edge and Chromium, I've had the unique opportunity to deeply engage with a wide array of technologies that shape today's accessible experiences. This includes web accessibility APIs, an assortment of assistive technologies (ATs), and platform-specific accessibility APIs across Windows, macOS, and Linux. My position has also afforded me the chance to collaborate with standard-setting bodies shaping the future of accessibility technology and to work in tandem with various Microsoft product teams striving to enhance accessibility. The insights presented in this document are a culmination of my years of observation and hands-on experience, particularly when encountering challenges and roadblocks in the field.

## Goals
* Articulate a forward-thinking vision for the future of web accessibility.
* Foster dialogue and collective action among industry stakeholders.
* Facilitate widespread innovation in the field of accessibility.

## Introduction: Accessibility is stuck
The web is advancing at an unprecedented pace, yet the progress in accessibility remains painfully slow. This stagnation doesn't just sideline those with disabilities — it risks deepening the divide. But don't mistake this lag for a lack of vision or willpower. Our community is buzzing with unprecedented levels of expertise and eagerness for change. The true culprits of this issue? A slow and clunky system to make improvements, cluttered by layers of bureaucracy, and a lack of extensible technology that would allow for fast prototyping when it comes to accessibility.

## Why is it stuck?
Despite rapid technological advancements, the progress in web accessibility has been sluggish. Several barriers contribute to this stagnation:

* A complex and bureaucratic system for approval and implementation.
* Limited and unscalable APIs for accessibility.
* A paradigm that ties assistive technologies primarily to graphical user interfaces, limiting their adaptability.
* A narrow range of available ATs, further restricted by platform-specific accessibility APIs.

### 1. Too many layers, too many stakeholders
1. Getting approval is slow: Say that you have a new idea to make websites adaptable for everyone's specific needs. First, you have to get this idea approved by a group that sets web standards. This can take months or years.
2. Then, the browsers must adapt: After gaining approval, all the web browsers have to start supporting your idea. Again, more years.
3. Next, operating systems: Even if you get this far, your idea has to be worked into the platform APIs for accessibility on Windows, macOS, or other OSes. Even more time.
4. Finally, supporting ATs: Once all previous steps are accomplished, the companies that make the technology to help disabled users must start supporting your changes. And guess what? This can take even more years, or might never happen.
As if navigating these challenges weren't complex enough, each stakeholder typically has a full agenda and is understandably cautious about committing to a new solution without the assurance that others are also on board. This situation can lead to impasses. Without a working prototype to validate an experimental solution, it becomes a difficult task to validate its effectiveness and gauge user demand.

When you work on the web platform or an OS platform API, it's easier to create new solutions because _you are_ one of the stakeholders. But when you're a web developer, you need to convince **three** other layers of stakeholders to follow your lead. This can be manageable if you're working on a web product owned by a Big Tech, for example, Word Online or Google Docs, because the company also happens to own a web browser and can help you push forward a proposal. But in the vast majority of instances, when you're on the outside, it's quite literally impossible to create something truly groundbreaking in the realm of accessibility.

### 2. Limiting APIs
The technical roadblocks are very familiar to anyone who's ever worked in the accessibility space as a browser implementor or a web standard contributor: 
- Limiting Web APIs: The only way to make web content accessible today is to use ARIA. The ARIA Working Group (ARIA WG) is the standard body responsible for making the web accessible to all. While it has done excellent work over the years (and still is!) to bring web developers an interface to make web content accessible, it isn't reasonable to ask of _one_ standard body to make all of the ever-changing GUI accessible to everyone, no matter their disability. This approach does not scale.
- Limiting platform accessibility APIs: Speaking from experience, it's much easier to push a change through the web standards than to push one through any of the platform accessibility APIs. Not only is it difficult - dare I say _impossible_ - to request an accessibility platform API to change, but the problem compounds when you recognize that each major platform - Windows, macOS, Linux, Android, iOS - has its distinct API for accessibility. While the web stands as a beacon of cross-platform compatibility, that ideal is compromised in the accessibility sector. Assistive technologies are built of platform-specific APIs, eroding the web's universal promise for individuals who need assistive technologies.

### 3. The Graphical User Interface (GUI) Paradigm
The accessibility APIs available on any major platform today are all designed to describe a *graphical* user interface rather than describe the structured data that was used to generate the GUI.

We currently see ATs as GUI accessors, similar to how we think of a keyboard or a mouse. While it's valid to draw a parallel between the usage a sighted user makes of a mouse to the one a blind user makes of a screen reader (both can control the GUI with it), it's limiting to see it only as such. Screen readers aren't just translating the visual interface; they're effectively creating a completely new user interface and user experience for blind individuals - much like a screen does to a sighted user - and the same is true for ATs developed to assist people with different disabilities as well.

Even though screen readers already create alternative user interfaces, those interfaces are biased to the visual interface displayed on the screen and its translation to the accessibility APIs. This therefore leads to what I call GUI-based assistive technologies, which are useful and necessary, but also have a limited upside in adaptable functionalities. Today's AT developers do not have any other choice but to use the platform APIs for accessibility on the different platforms, and because these APIs are focused on translating the GUI, they can't decide to go ahead and build a fully optimized and adaptable user interface of a different medium for a user with particular needs - they don't have the tools, so they have to be heavily dependent on the GUI.

I believe we can do better; nothing forces us to remain dependent on the GUI to power accessible experiences. Instead, we have the opportunity - and responsibility - to build the technologies and APIs of tomorrow that will enable the best ultimate accessible experiences without constraints on other mediums.

### 4. The bottleneck of AT availability and flexibility
One of the often-overlooked issues in the realm of web accessibility is the limited availability and extensibility of Assistive Technologies (ATs). For instance, consider the screen reader landscape: it's dominated by just a handful of solutions — about three for Windows, one or two for Linux, and singular options for Mac, iPhone, and Android. Of them all, only one screen reader on Windows and two on Linux are open source and welcome edits from the community.

All of these screen readers consume the platform APIs for accessibility, which makes it impossible for a new web-based feature to be passed down through the system to the ATs that could consume it without also modifying said platform APIs - i.e. modifying the OSes themselves and the web platform.

## What's the cost?
Innovating in the realm of accessibility is extremely difficult and at times impossible. This impacts a wide range of individuals, organizations, and businesses. 
The following breakdown elaborates on two primary areas affected by these constraints:
* Impact on people with disabilities: They often face inadequate digital experiences, widening the accessibility gap.
* Financial and time costs: Innovating in accessibility is both time-consuming and costly, discouraging new advancements.

### Impact on people with disabilities (PwD)
The impact on people with disabilities is the most straightforward: PwDs often have a subpar digital experience. Since accessibility is unfortunately often just an afterthought in the design process, PwDs also have access to some experiences/products/features at a later time than the rest of the population. It has been reported so many times that there's an existing (and **widening**) divide in terms of opportunities in education, employment, and entertainment availabilities between people with disabilities and people without. This gap will continue to grow until we finally empower developers on the most thriving platform to create innovative solutions too.

### Financial and time costs
Organizations and individuals who want to innovate and iterate on a new accessible experience either simply can't or would have to spend a lot of time and money to make it a reality. For example, when a web app wants to create a new sort of UI control that can't be exposed to ATs using the existing properties in the accessibility APIs, the web author needs to involve members of:
* the web platform working on a web browser, like Microsoft Edge engineers
* The standard bodies working on accessibility
* the OS team in charge of the platform accessibility API
* the assistive technology you're targeting.

When you calculate the individual costs and consider the time required to implement new accessibility features in the web platform, it becomes clear just how costly the process is. For a concrete example, see the AriaNotify section below.

## Examples
To further illustrate the complexities and barriers to innovation in web accessibility, let's consider two real-world examples. These shed light on the headaches that developers and organizations face when trying to make improvements to accessibility fundamentals.

### AriaNotify
Historically, the quality of accessible notifications on the web has been less than ideal. For screen reader users, some websites send so many unimportant notifications that they sometimes prefer to turn off the entire notification feature. This issue has been recognized in the standards community for some time; I came across a [discussion from five years ago](https://github.com/w3c/aria/issues/832) that centers on this very topic.

My colleagues and I, who are spread out across multiple projects at once, have been working part-time on [a proposal for a better mechanism to fire accessibility-related notifications](https://docs.google.com/document/u/0/d/17kKNoCIoMSFMFicz0wSQR-PHWHfHGYfz1WdtHMYyrhE/mobilebasic) to ATs from the web content. The work started **over two years ago**; yet, we still have never seen a prototype of this proposal. While it is expected for standardized solutions to be worked on for a long time before being finalized, prototyping should never take this long, nor should they have to go through the standard bodies before thorough experimentation.

While we do have an "easy" way to prototype and experiment with new solutions in Microsoft Edge before we standardize a solution (and this is what we're finally about to start in the coming weeks), we decided to hold off until now for two reasons: 
* Our ideal solution would require changes to the platform accessibility APIs and changes in ATs themselves.
* We wanted to have feedback from the community and standard bodies on how to operate to drive the _right_ solution.

Iterating by incorporating user feedback in an experimental solution is not a possible thing to do when in the accessibility space. This is an unreasonable expectation that I don't think anyone ever wanted, but has been forced onto us by years of limiting APIs and fragmented vision.

### Aria Virtual Content
My team and I have also been working on another proposal, [aria-virtualcontent]((https://github.com/WICG/accessible-loading-and-searching-of-content/blob/main/explainer.md), which encountered obstacles and was blocked during the prototyping stage. This proposal seeks to address the challenge of making 'virtual content' accessible. Virtual content refers to elements that don't appear on a web page at the time of its initial loading but emerge later—such as in an infinite scroll feed or an expansive Word document—making them inaccessible to users who depend on assistive technologies.

This time, we did build a prototype directly within Chromium and Microsoft Edge for user testing but were blocked due to a lack of commitment from any major screen reader to go ahead and consume the new properties we were exposing as part of this new solution. Unfortunately, this prototype has been blocked for over two years and moved to the back burner ever since, even though this is still a very active issue AT users are facing.

## Solutions
To reiterate, the problem comes in part from the many layers that need to be modified to introduce breakthrough improvements in the accessible experience:
1. Web app 
2. Web standards
3. Browsers
4. OS APIs for accessibility
5. Assistive Technologies

> While some browsers like Microsoft Edge and Google Chrome have a built-in mechanism to experience non-standardized APIs (like we did with aria-virtualcontent and like we're about to start doing with ariaNotify), this still requires that a developer who wants to create something new knows how to contribute changes to the web platform, which is an extensive process. A minority of web developers know how to modify a browser, so I don't believe we should seriously consider this as a real alternative.

The high barriers to entry and the complex landscape of platform-specific APIs discourage new players from entering the field. This lack of competition perpetuates a stagnant market, reducing the incentive for existing solutions to innovate and improve. Ultimately, this leads to a vicious cycle that perpetuates and accentuates the impact on PwDs and people trying to innovate. Any solution that will lead to easier prototyping of accessibility-related features needs to consist of a way to break through the first three layers and facilitate AT modifications. 

### How do we break this cycle?
Essentially, I believe we need to democratize innovation: give the power to create new accessibility technologies to developers and let them create new things.

I see 3 ways forward, ordered from "easiest" to most involved:
1. "ARIA extensions": an API to allow for passing any types of data, and modifying the platform APIs for accessibility to pass this new information to existing ATs.
2. Universal UI API: a new web API to allow for serializing information unrelated to the GUI, and creating equivalent information API on the platform levels.
3. Web AT: just like the web engine is responsible for its rendering of the GUI, it could be responsible for the rendering of the accessible UI in the web platform.

### 1. "ARIA Extensions"
If web authors had a way to pass custom properties, fire custom events, and respond to custom commands, there would be no need to modify a web browser and its web platform just to prototype a new feature nor would there be a need to modify a platform accessibility API - the custom information would simply be serialized with the "ARIA extensions" system implemented in the browser and plumbed through the system-level. Web authors would still have to modify an AT to prototype the feature, which remains a complex task, but a much more manageable one than modifying standards, a browser, and platform APIs. This approach would democratize innovations in the accessibility space.

This solution would allow us to remove three of the 5 layers of edits I mentioned before:
1. Web app 
2. ~~Web standards~~
3. ~~Browsers~~
4. ~~OS APIs for accessibility~~
5. Assistive Technologies

Let's dive in. 

The ARIA extensions proposal I introduce here would be composed of 3 parts:
1. Custom properties (to share with an AT)
2. Custom events (to notify an AT about a change)
3. Custom commands (to allow an AT to produce a predetermined action on the web page)

Here's an example in JavaScript to demonstrate how it could be used:

Let's say an author wants to propose creating a habituating experience for chat components, like the ones we find in Microsoft Teams, Bing chat, Amazon's Customer service chat, or Facebook Messenger. They want to create a shortcut in a screen reader to read out loud how many unread messages there are, or how many participants there are in the chat. To experiment with passing this custom data from their web app, they could simply call the following JavaScript API:

let chatExtension = AriaExtension("CompanyName.Experimental.HabituatingChatExperience")
document.getElementById("my-chat-root-element").ariaExtensions.push(chatExtension);

The first thing to notice here is that the extension would be created taking a unique identifier so the ATs can distinguish it from other extensions.
The second thing to notice is that the `ariaExtensions` attribute is a DOM element attribute and an array that can contain multiple different extensions. This would allow simultaneous extensions to be supported for the same element.

Next, the web author could then pass their properties by creating a custom set of properties, like this:
```
chatExtension.addPropertySet({
  setIdentifier: "MetadataProperties",  
  data: {
    "numberOfUnreadMessages": 5,
    "numberOfParticipants": 3,
  },
});
```

Once again, the set would take a unique identifier. That identifier must be unique within this extension and would allow for multiple different sets of properties to be part of this extension. The data object would contain all of the key-value pairs that must be transmitted to the AT.

Using a similar interface, the web author could update the properties in that bundle when necessary:
```
chatExtension.updatePropertySet({
  setIdentifier: "MetadataProperties",
  updatedData: {
    "numberOfUnreadMessages": 6, // Only updated properties need to be in there - no need to repeat what has already been shared previously.
  },
});
```

The web browser would then have the ability to automatically generate custom events for this extension when a property value changes (this could be left at the discretion of the web author), so the ATs are always notified of the latest information and the web author doesn't have to manually do what can easily be automated.

Then, if they also wanted to fire a custom event whenever someone sends a message, they could fire it with the following structure:

```
chatExtension.raiseEvent({
  eventIdentifier: "myNewCustomNewMessageNotification",
  extension: {
    "sender": "Benjamin Beaudry",
    "time": "2023-09-12 17:33:47 PST",
    "chat-name": "Accessibility discussions"
  }
});
```
In this example, sending custom properties with events opens new AT capabilities, such as announcing message senders or helping users identify the message channel quickly. A supporting screen reader could also decide to play an earcon for a new message, for example, or even allow the user to customize the tone of the earcon depending on the sender of the message.

Finally, let's say that our innovative web author wants to easily build into this AT chat UI an easy way for the AT user to mark all messages as read. Using the command functionality of this extensions API, the author could easily do something like this:

```
function markAllAsRead() {
  // Your logic here.
}

chatExtension.registerCommand({
  commandId: "markAllAsRead",
  callback: markAllAsRead
});
```

The AT manufacturer could then decide to leverage the "markAllAsRead" custom command to run this command in the web app when a specific shortcut is pressed.

> This type of command pattern would allow web authors to detect when a user relies on an AT, allowing for fingerprinting and breaking the privacy of the user. While the command part of this proposal is not necessary to allow web authors and AT manufacturers to innovate, I think it offers a lot of upside as well and I wanted to include it for the discussion.

Once this custom extension is baked into an AT, any web author who would like to start supporting it in their web app could then simply reuse the extension with that identifier and pass their data to it, unlocking a brand-new accessible scenario with minimal effort. Coming back to my previous example, if Microsoft Teams, Bing Chat, Amazon's Customer service chat, and Facebook Messenger would all start supporting this new chat extension, users of the ATs supporting this extension would benefit from a familiar and habituating UI.

#### Advantages
* No need to modify the web platform to allow for custom properties/events/commands to be made.
* No need to modify a platform API for accessibility to pass this custom information.
* Very short development time for anyone trying to create something new.
* Easy-to-use interface.
* The browser can automatically generate custom property changed events when a custom property changes.
* Lastly, one of the most important benefits in my opinion: Possibility to create habituating experiences for complex UI components, like the chat interface I mentioned here. Any product team could reuse an existing community-approved extension for minimal cost and get all of the great AT support out of the box.

#### Disadvantages
* This might get messy quickly. What if two extensions share the same name, or are used with malicious intent?
* Still necessary to have knowledge, resources, and capacity to edit an AT. NVDA Add-ons could be an option here, although limited to Windows and NVDA itself.
* Privacy issues and fingerprinting are possible with the commands part of this proposal.
* This API could be exploited to pass _any_ type of information, even stuff unrelated to accessibility, down to the system level for other applications to use. This unexpected usage of the API could have larger implications. After all, this is essentially an "everything" API, and it could be a dangerous precedent to set.

#### Areas of improvements
This is nothing more than the draft of an idea, and I see many ways in which it could evolve: 
* Limit this API for experimentation. Give the user the control to enable the ARIA extensions through a feature flag in the browser - and disable it by default - so web authors don't start relying on this API for other use cases than prototyping and experimenting.
* On the contrary, enable this API by default and standardize it so that some extensions because official standards.
* Bake an inheritance mechanism into the extensions, so an organization or individual can iterate over an existing extension and inherit all the existing properties, events, and commands.
* Explore ways to replace the string-based key-value interface with something typed, like JSON schemas.

### 2. Universal UI APIs and generative UI ATs
This idea is a step up in complexity from the previous proposal. It calls into question the existing orientation of popular ATs and platform-level accessibility APIs, which are geared more toward GUI translation. The proposal also suggests a shift towards providing organized hierarchical information, which could be the foundation for building a completely adaptable UI, rather than just helping users navigate through a predefined GUI. To clarify, I'm not diminishing the value of GUI-based ATs; instead, I'm emphasizing that a sustainable, long-term solution needs to go beyond mere translation from one medium to another. Screen readers and similar GUI-focused ATs will always serve a purpose, but the current gap in the AT landscape stems from a significant shortfall in adaptable accessibility APIs.

#### The Concept
Imagine a system capable of crafting a customized UI for each user, taking into account their unique requirements:

* For sighted users: an optimized graphical interface that auto-adjusts based on visual impairments like color blindness.
* For blind users: a tailored audio interface.
* For deaf-blind individuals: a specialized tactile interface.
* For those with cognitive or learning disabilities: a UI designed to minimize cognitive load, shorten text, etc.
* etc.

The heart of this system lies in this proposed Universal UI Accessibility API that feeds raw, structured data into a new type of UI-generating ATs, allowing for this level of customization.

Accepting this new paradigm would not only empower developers to build technologies that fit the special needs of people with disabilities, but it would enable an entirely new industry of adaptable user interfaces; things like audio interfaces with voice control that allow for complex website interaction, haptic and tactile devices that augment the user interface or unlocks completely new ones and simplified/customized graphical user interfaces. The use case of these interfaces extends far beyond the accessibility; it could be useful for anybody.

Transitioning from a GUI-focused approach to one rooted in universal UI centered on raw content would be a game-changer for the industry, potentially paving the way for a more diverse range of genuinely accessible technologies.

#### Design Principles
To prevent the shortcomings of previous models and APIs, this Universal Design APIs should follow specific principles:
* Content-Centric: Accessibility tools must access the raw content data, not just its visual representation.
* Future-Proof: Given that UIs are constantly evolving, the API should be designed for extensibility without assuming a limited set of UI components.
* Flexibility: Developers should be able to tailor any aspect of the UI and customize it, the same way they can today with GUI on the web.
* Asynchronous Operation: Complex applications, like web browsers, have a multi-process architecture that doesn't allow them to service a synchronous API without a heavy compromise on performance and security. Any new accessibility API should be designed to work asynchronously.

#### Advantages
* If the Universal UI API is effectively implemented and at least one UI-generating Assistive Technology is built to complement it, personalized user interfaces tailored to individual needs could be generated. This would make apps accessible by default.
* Streamlines the development process. Developers could generate UIs automatically, focusing their efforts on more complex tasks. It’s an optional feature that would be particularly beneficial for smaller projects.
* An extensible Universal UI API and digital UI generator could be leveraged to make the physical world more accessible to blind or deaf individuals. 
* Many more potential users.
* More users -> bigger market -> more competition -> more innovations

#### Disadvantages
* A lot of engineering work is required to make this happen, and many stakeholders need to be involved.
* New ATs would have to be built/existing ATs would have to be updated.
* Learning curve for our users to learn to use the new assistive tools.

#### Areas of improvements
The idea of building a technology that would enable alternative generative user interfaces is powerful. More work is needed to develop this idea further. Here are some starting points for a follow-up discussion:
* AI Integration: How can emerging technologies like AI be integrated into this framework for even more dynamic and adaptable UIs?
* Long-term Support: How will the Universal UI API adapt to future technological changes to ensure it doesn't become obsolete?
* Iterative process: What steps can be taken to ensure that this project progresses through a series of incremental improvements?

### 3. Web-based AT
This final approach not only builds upon the previous suggestions but also takes them to the next level.

The idea is simple: The web platform, which already offers its cross-platform rendering engine for GUI and so many developer tools to customize it, should start building its own web-based cross-platform AT that lives in the browser. The browser and the web would then not simply be the middleman between web content and ATs anymore but would evolve into its accessibility rendering engine.

This is a *very* ambitious idea, but I think it's important to go over why this should be considered as possibly the best long-term solution.

#### Advantages
* Maintains Web Platform Security: Acknowledging that ATs should solely be OS applications implies that we must send all confidential user data from every website through a publicly accessible API, which is vulnerable to unauthorized access. (Note: macOS does require initial user permission for API access, but afterward, it becomes as openly accessible as on other platforms). A web-based AT would allow us to keep the user data in the browser.
* Keeps the web platform cross-platform: delegating the role of creating ATs to the OS is accepting that ATs will be different from one platform to the other, and that web authors can not benefit from building single products that run everywhere flawlessly. It's also accepting the fact that web users might have subpar experiences when on one OS vs. another while claiming that our platform works the same way for users without disabilities across all platforms.
* Faster iteration: Controlling an open and standardized accessibility experience from end-to-end on the web platform would allow for faster prototyping and lead to more innovations.

#### Disadvantages
* A lot of engineering work is required to make this happen, and many stakeholders need to be involved.
* More resources would be required on the web platform and standards community.
* Learning curve for our users to learn to use the new assistive tools.

#### Areas of improvements
* Modular ATs: If the web browser is to have its own AT interface, it needs to work well with the one at the OS level. For example, we can't have a screen reader on the OS and a screen reader in the web browser that simultaneously reads content from a web page. One knows when to delegate to the other, thus why we might need a new protocol for modular and nestable assistive technologies.

## Next steps
My goal with this document was to go over what I believe to be the largest problem in the accessibility space and to introduce possible areas of improvement. While the ideas presented here may not yet be fully formed to stand independently, I hope they are substantial enough to initiate a meaningful discussion on the subject. Needless to say, any of these solutions would involve a large number of individuals, standard bodies, and organizations cooperating and a large upfront investment. I am confident that, over time, the initial investment will yield returns by lowering the costs of current solution implementations and by increasing both social and financial benefits through expanded user engagement.

Whether you agree or disagree, contributions of any kind are welcomed! Please take an active part in improving the future of digital accessibility by contributing to the discussion in the issues section of this repo, or by filing a new one.
  
