# safer-methodology

this is just a little memo I'm putting together to encapsulate something about my general principles I have toward projects that I've been thinking about lately, the driving philosophy that motivates my decisions when I'm drawing up a project plan

the pillars that the letters currently stand for are **Sustainable**, **Accessible**, **Foundational**, **Extensible**, and **Reversible**. These aren't really the things at the forefront of my mind, I'm just picking them because I want an acronym to convey this that's easy to use as a rallying flag for the general zeitgeist (like REST), something that points toward what kinds of specific guidelines *would* and *would not* fall under this ideology (so there's nothing that says, like, "use whatever gets the job done", because that doesn't actually satisfy the criteria, even though it sounds like the kind of pragmatic advice that'd be something I'd say)

### Sustainable

I guess this basically means not doing anything that fundamentally, mathematically, can't work when scaled up. I'm not talking about the kind of things Paul Graham was talking about when he said "do things that don't scale", where they can be replaced with something more suited to larger scales at such point as that is realized (ie. projects requiring Raspberry Pis once demand got high enough that they could be made mass-available for $35): I'm talking about crap like Bitcoin where every node on the network is expected to be aware of every transaction that's ever occured, and can't cope with 51% attacks.

### Accessible

don't make stuff that runs on a $30000 machine just because you personally have access to one and you didn't feel like figuring out how to make it run on a $30 machine.

don't design stuff that relies on aspects of your particular environment, like a windowing system or authentication server that assume you're running specific computers on a specific kind of network developed exclusively for MIT. (thanks a lot, X11, you narrow-visioned piece of crufty legacy garbage)

don't use slang and jargon that isn't explicitly explained to outsiders in some kind of public Jargon File (and even then, don't get too attached to any one way of saying anything).

### Foundational

make your designs something that can be built off of

make as few assumptions about the layers above/below your stack as possible, so they can change without bitrotting your work

don't freaking link in minor deps that have licensing restrictions you don't want to apply to your peoject at large. part of what drove me to write this is that, for the last couple years, I've been looking for a good open-source photogrammetry stack that I might use in conjunction with some kind of 3D capture consulting, and *every damn one of them* linked in the academic SIFT algorithm for one step, that has a licensing restriction that you can't use it for commercial use - meaning that, if I wanted to legally use something for this consulting business, I *could not contribute back*, because the only options  that didn't have encumbrances like this for non-purely-academic purposes were proprietary commercial abominations. all this could have been avoided by the authors of this stuff taking a second to *think about the damn implications outside their narrow focus of endeavor*, but it wasn't until I did a search earlier today that I *finally* read an article about somebody who made a structure-from-motion suite like this without such a restriction - and part of the work that had to do was *going out and painstakingly stripping SIFT out from all of their dependencies, just because the original authors hadn't cared enough to do so themselves*. Asinine.

### Extensible

this kind of overlaps Foundational a lot so if I keep this as a descriptor I'll probably split half the stuff I just described under Foundational into this

### Reversible

don't lock anybody into your specific way of doing things

use non-destructive transformations and non-lossy conversions, keep backups, keep your source inputs wherever possible

don't make anything where, if the user / developer / operator / reader messes something up, they can't try again without having to replace the thing they just broke (unless it's fundamentally unavoidable)

## derived guidelines

these are the direct effects of the philosophy I'm trying to encapsulate, the implications and realizations of the principles in the acronym.

some of these aren't well covered in the acronym right now (see "state of this memo" below), but it's *this* stuff that I'm looking to drive the acronym, and not the other way around: I want people to see what I'm seeing, in a quick-to-absorb brain-patch that can correct all the little pain-in-the-ass mistakes nobody has to make so long as they're thinking about this stuff.

### general project practices

- document everything (foundational). document EVERYTHING. publish your rough drafts. if you have a choice between being messy and being completely silent (because you don't have time to clean what you've got up), be messy - the worst that can happen (so long as you're clear about what you're being messy about) is it gets ignored. with luck, someone will be able to take at least *something* from your messy work and use it (hopefully you'll be alive for them to ask you for better details), and maybe they'll even be able to clean it up for you with time that *they* have
- edit your rough drafts into something another person could follow (accessible)
- name things. pick something that'll win in the Google search results - don't name your window manager "awesome", don't name your programming language "go". (accessibility and/or foundationality? this helps people track your project's lineage down when it's cited as an influence) more practically, I mean give your projects clear specific-to-you names like how MakerBot had "Cupcake CNC", "Thing-o-Matic", and "Replicator", and don't do things like just calling your printer "Clone R1 Dual", so people can't tell the difference between a writer talking about *your* Clone and a writer talking about *any* clone.

### software practices

- don't rely on proprietary components for anything that you couldn't replace yourself in under a week. (foundational)

### in hardware (3d print designs, Internet of Things, System on a Chip, stuff like that), this means:

- not requiring tools beyond stuff you can get at a dollar store like screwdrivers (accessibility)
- not requiring parts you can't 3D print unless absolutely necessary (ie print snaps, not screwholes) (accessibility - it's *exponentially* more effective for the print author to take a few hours of their time to do this than make a hundred people printing it to dedicate hours of their own time to go out to the hardware store - I almost said this is "just convenience", but what's "convenience" to you can be a deciding factor between what's prohibitive and what's not for someone else)
- not requiring soldering or even plugging in things with connectors that can be seated backwards (the way building a PC is) (accessibility, reversibility)
- not requiring the user to know anything you have to go to a school for (accessibility)
- not requiring cutting, drilling, tearing, or supergluing anything (reversibility)

## state of this memo

this is really really really rough right now, and I just came up with that acronym like half an hour ago, so don't go spreading it like gospel until I've ironed out exactly what I'm driving at here. that's how Object-Oriented programming decayed from Alan Kay's expansive functional paradigm into a garbage dogma of mediocre spelling in the mass consciousness. it's not that it's *impossible* to invent a decently-followed ideology, it's just that you really have to make sure it's fully baked before you go out and serve it on the streets

there's no actual space in the acronym right now for the role of pragmatism (over dogmatism), for instance, and while that's the kind of thing that, like, I'd rather be left out entirely, than be kept in with the potential to be misinterpreted ("how could the step where you have to exclusively run your email through a proprietary server running from my house be violating this spirit? I'm doing it in the name of *pragmatism*"), there's something to be said for Torvaldsism over Stallmanism (for example, GitHub's not a perfect place to host open-source projects, but it's *way* better for accessibility in that you'll get exposure to a broader community than eg. GitLab).

really the "sustainable" and "extensible" words, looking at what I've written so far, are more buzzwords I put in for other people to latch onto (vecause they're the ones people use to describe agjacent projects in spaces like this) than anything I particularly care about - they're both kind of moot points in the presence of "foundational", which eclipses their entire (myopic, imo) focus to drive at the heart of what I'm *really* looking toward: you need to make something that's so fundamentally sustainable and extensible that someone else can use it *as the basis for their own work*, even if that means copying what you did and mangling it until it's barely recognizable (but maybe using copyleft clauses to ensure they don't mangle away extensibility or sustainability).

everything about this document should be expected to change, including *especially* the name. even calling it a "memo" is subject to change, because that's kind of dumb, and is mostly something I'm doing so I don't get paralyzed with gravitas or whatever right now and stop myself from writing anything down at all. (see my previous "meditations" and "barfspace" projects if that sounds like a fun topic to read about at unpolished length)

like what I'd really rather have is a rubric that's structured like an RFC, with MUST and MUST NOT criteria you can gauge against, something like the Joel Test where anything less than a near-perfect score daren't call itself SAFER
