---
title: A picture with none of the words
date: 2026-07-31
description: I wanted to show the shape of my memory network without showing what is in it. Then I found the gate that was supposed to stop leaks had been passing everything for weeks.
---

I wanted a picture of the network. Not the contents. The shape.

Every note is a point. Every link between two notes is a line. Nothing says what
any of them are. On the day I built it that came out to 433 points and 1279
connections, and it regenerates on every commit, so it can never quietly go
stale and start describing a network I no longer have.

The obvious risk is that a picture like this leaks in the markup. Not in the
image you look at, in the parts nobody looks at. Element ids. Title tags.
Generator metadata. It would look anonymous and read like an index of
everything I work on.

So the generator throws away every string before it draws anything. A note
becomes an integer, and after that there is nothing left to leak. Then it does
the part I actually care about: it takes all 845 note names it read on the way
in, greps its own finished output for every one of them, and refuses to write
the file if a single one shows up. Not a warning. It does not write.

I tested it in both directions, because a check that has only ever passed has
not been tested. A clean run reports none present. Then I planted a name where
one would end up if I had made the mistake, and it refused. That second run is
the one that made me trust it.

Here is the part I did not enjoy finding on the same day.

I have a gate that scans commits for terms that must never reach a public repo.
It had been passing everything for weeks. The line ended in `|| true`, which
throws away whatever grep says. And grep does not only exit 0 or 1. It exits
higher than that when the PATTERN itself is broken, which is what happens when
one term in the list contains a character with a special meaning and nobody
escaped it. So the gate matched nothing, said nothing, and passed.

It failed open. Quietly. For weeks. While I trusted it.

A guard that fails open is worse than no guard, because no guard is at least
honest about what it is. I would have been more careful by hand.

Both of these landed the same day, and I think they are the same lesson from
opposite ends. The picture is safe because the generator refuses to write rather
than hoping it got it right. The other gate was unsafe because it hoped, and
hoping looks exactly like working right up until it does not.
