# The SACRED Tenets of Foundational Architecture

This is a little memo (for now) that I'm putting together to encapsulate my general philosophy around what it takes for a project to be really worth building, and worth building upon. The need for a statement to this effect came to me when I was looking at projects in the 3D printing space, but it also applies to projects in further domains, like software, and even policy initiatives.

The letters in SACRED stand for **S**traightforward, **A**ccessible, **C**omprehensive, **R**eversible, **E**xtensible, and **D**escriptive.

### Straightforward

Nothing in the system should be made more complicated than it needs to be to safely function. If there's a wall that would have no purpose other than to obscure the inner workings from the user, you leave it out: machinery you can see and understand is *far* more beautiful than some bland decoration standing in the way and making the thing harder to repair.

Keeping your design straightforward and transparent avoids running afoul of [The Law of Leaky Abstractions][], where attempts to make things *appear simpler* often result in working with them becoming *more complex*. As the "New Jersey approach" of [Worse is Better][] holds, the guiding factor when designing an interface to be useful should be the simplicity of its implementation.

As [The Design of Everyday Things][] describes, people learn to use things most naturally by watching them work: the harder you make it to understand, the harder it'll be to use (and to extend, and to reverse, and to describe... an affront to the whole methodology, really).

[The Law of Leaky Abstractions]: https://www.joelonsoftware.com/2002/11/11/the-law-of-leaky-abstractions/
[Worse is Better]: https://en.wikipedia.org/wiki/Worse_is_better
[The Design of Everyday Things]: https://www.amazon.com/Design-Everyday-Things-Donald-Norman/dp/1452654123

### Accessible

Don't make stuff that runs on a $30000 machine just because you personally have access to one and you didn't feel like figuring out how to make it run on a $30 machine.

Don't design stuff that relies on aspects of your particular environment, like a windowing system or authentication server that assume you're running specific computers on a specific kind of network developed exclusively for MIT. (thanks a lot, X11, you narrow-visioned piece of crufty legacy garbage)

### Comprehensive

In places where the project is not in control of its surroundings, it should make as few assumptions about them as possible.

The project should include as much of what it needs as it can, or ensure that its dependencies will be readily and easily available. It sould not require disproportionately large dependencies for minor things (ie. requiring a power drill or larger machinery, to drill a single hole for a single step).

The project doesn't have to be responsible for everything itself, but it has to have an *answer* for everything, even if those answers are just suggestions for other elements to incorporate to solve the problem. (It needs to work *well* with those suggested things, though; you can't just fire off a guess that the first person to try will discover was a terrible idea.)

### Reversible

Don't lock anybody into your specific way of doing things. Cooperate with other ecosystems. (This also ties into Extensibility.)

Use non-destructive transformations and non-lossy conversions (with data, keep your source inputs available wherever possible, and keep backups of anything you need to replace).

Don't make anything where, if the user / developer / operator / reader messes something up, they can't try again without having to replace the thing they just broke (unless it's fundamentally unavoidable).

### Extensible

The project should be released under a license that permits modification.

Modularity is an important component of extensibility. Avoiding connecting things that don't need to be connected allows them to be upgraded and replaced piece-by-piece. Decoupling the assumptions of one part from the circumstances of another allows future improvements to resolve issues arising from those circumstances without breaking backwards compatibility.

### Descriptive

Don't use slang and jargon that isn't explicitly explained to outsiders in some kind of public Jargon File (and even then, don't get too attached to any one way of saying anything).

Document **everything**. While you're working on the final release, publish your rough drafts (and keep them available for development insight). If you have a choice between being messy and being completely silent (because you don't have time to clean what you've got up), be messy - the worst that can happen (so long as you're clear about what you're being messy about) is it gets ignored. With luck, someone will be able to take at least *something* from your messy work and use it (hopefully you'll be alive for them to ask you for better details), and maybe they'll even be able to clean up the things you disn't have time to polish in the time that *they do* have.

Whenever possible, though, you should edit your rough drafts to make sure that they're easy to follow (this also overlaps with Accessibility).

Give the project (and each of its internal parts) a descriptive, unique name. Pick something that'll win in the Google search results - don't name your window manager "awesome", don't name your programming language "go". (Before I settled on this name, I did a search for "sacred tenets" to see if that had a particularly-prominent publication that would be higher to overcome in popularity: most of the results seemed niche enough for this to be the main thing described by that phrase.)

## The Tenets in Practice

### In software development

- Don't rely on proprietary components for anything that you couldn't replace yourself in under a week. (Accessibility, Comprehensiveness)
- Make as few assumptions about the layers above/below your stack as possible, so they can change without bitrotting your work. (Comprehensiveness)

### In 3D-printed things

- Not requiring tools beyond stuff you can get at a dollar store like screwdrivers. (Accessibility, Comprehensiveness)
- Not requiring parts you can't 3D print unless absolutely necessary (ie. printing snap-fit fasteners instead of screwholes). (Comprehensiveness)
- Not requiring soldering or even plugging in things with connectors that can be seated backwards (such as how most connectors in PC building are designed). (Accessibility, Reversibility)
- Not requiring the user to know anything you have to go to a school for. (Accessibility)
- Not requiring cutting, drilling, tearing, or supergluing anything. (Reversibility)
