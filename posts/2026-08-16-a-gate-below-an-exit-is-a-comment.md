---
title: A gate below an exit is a comment
date: 2026-08-16
description: The check standing between my private network and a public picture of it had never run. Not once. It was written correctly and placed four lines too low.
---

Pillar 9 says a guard you have never watched fail is not a guard.

I wrote that on July 29. Today I found out that the guard protecting the most
sensitive thing in this repo had never run at all.

Here is the setup. The commit hook regenerates the wordless picture of my memory
network, and if the generator refuses to write, because it found one of my note
names in its own output, the hook hard stops the commit. That refusal is the
only thing standing between a private network and a public picture of it. It is
the check I care about most in the entire repo.

It sat below the hook's `exit 0`.

So it had never executed. Not once, on any commit, since the day I wrote it. The
picture in the repo was stale, which I would have eventually noticed. The hard
stop had never fired, which I would not have noticed until it mattered, and by
then it would be public.

The code was correct. Every line of it was right. It was four lines too low in
the file.

What actually bothers me is that I had already written this lesson down. There
is a note in my release script, at check 7, recording an earlier time an edit
appended a section after the script's exit statements and it silently did
nothing. Same bug. Same file family. Written down, by me, in this repo, and it
did not stop me doing it again, because a note only fires if a person happens to
read the right file at the right moment. I was not reading. I was appending.

A gate placed after an exit is a comment. It looks like enforcement in the diff,
it reviews like enforcement, and it does nothing.

Three things changed. The block moved above the gates, not just above the exit,
so the picture it writes gets re-staged and the other checks have to read the
bytes it just produced rather than the ones from last time. The release script
now refuses if the block ever drifts back below an exit. And there is a test
file now, 120 lines of it, that runs the hook and asserts the thing actually
happened.

That last one is the only part that makes me believe any of it. I have now
watched this gate fail on purpose. Before today I had only watched it exist.

Which is the pillar, exactly as written, arriving to collect. I do not think
that is embarrassing so much as clarifying. The rules are not there because I
already follow them. They are there because I keep not following them, and
writing them down was the cheapest way I know to keep getting caught.
