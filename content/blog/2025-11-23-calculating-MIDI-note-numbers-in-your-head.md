---
title: Calculating MIDI note numbers in your head
date: 2025-11-23
categories:
  - music
tags:
  - ResourcesForComposers
  - music-theory
  - math
  - computer-music
description: Translating between MIDI note numbers and scientific pitch notation is straightforward if you have your multiples of 12 memorized.
ogimage:
---
I can think of a few reasons why you might want to be able to translate between [scientific pitch notation](https://en.wikipedia.org/wiki/Scientific_pitch_notation), or SPN, staff notation, and MIDI note numbers quickly, in your head, without looking at a table. Maybe you’re a composer doing algorithmic composition, maybe you’re working with a MIDI roll in a DAW, maybe you’re a computational musicologist, or maybe you just want to impress your students (:eyeroll:). To do this, two things are required: 1) know the multiples of 12 (either by rote memorization, or with a quick mental calculation); 2) instant recall of pitch class numbers.

## Scientific pitch notation vs MIDI

The key thing to note is that SPN and MIDI note numbers both work on assigning the different octaves of pitch class $C$ to multiples of $12\\.$ The hitch is that they are off by $12$ with respect to each other. Middle $C$ in SPN is designated as $C_4\\,$ while in MIDI, middle $C$ is note number $60\\,$ or $5 \times 12\\,$ or the $5th$ octave.

|  $C_{-1}$  | $C_0$ | $C_1$ | $C_2$ | $C_3$ | $C_4$ | $C_5$ | $C_6$ | $C_7$ | $C_8$ | $C_9$ |
| -------- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- |
| $0$      | $12$  | $24$  | $36$  | $48$  | $60$  | $72$  | $84$  | $96$  | $108$ | $120$ |

So, to translate a $C$ from SPN to MIDI, just add $1$ to the octave. $C_2$ becomes $12 \times 3\\,$ or MIDI note 36. Now, to translate *any* note name in SPN to MIDI, we just need to add the pitch class number of the note to the number for $C$ in the correct octave, and we are done.

Some examples:

To find the MIDI note for $G_3\\,$ we need to know that the pitch class number for $G$ is $7\\,$ which we add to the next higher multiple of $12$:

$$G_3 =(12 \times 4) + 7=55$$

To find $E\flat_9\\,$ we need to add $3\\,$ the pitch class number for $E\flat\\,$ to the $10th$ multiple of $12$:

$$E\flat_9=(12\times10)+3=123$$

Now, let's do the reverse. For MIDI note number $89\\,$ we see that it is between $84$ and $96\\,$ so that it is the $7th$ MIDI octave. That means it will be in the $C_6$ octave in SPN. $89=84+5$, so the pitch class is $5$, which is the pitch class $F$. So the SPN name for this note is $F_6$:

$$89=(12\times7)+5=F_6$$

## Memorizing, or quickly calculating, multiples of 12

OK, that is straightforward, but what if you don't have pitch class numbers or multiples of $12$ memorized? In the case of pitch class numbers, there's no way around it. These need to be memorized in order to work effectively with music theory past, say, the 1960s. As for multiples of $12$? I did a quick poll on Mastodon, and over half the respondents indeed had their "12 times tables" memorized since school days. So where does that leave the rest of us?

Let's take a look:

| $0$ | $1$ | $2$ | $3$ | $4$ | $5$ | $6$ | $7$ | $8$ | $9$ | $10$ |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| $0$ | $12$ | $24$ | $36$ | $48$ | $60$ | $72$ | $84$ | $96$ | $108$ | $120$ |

The first thing we might notice is that the last digit follows a repeating sequence: $0, 2, 4, 6, 8, 0, 2, \ldots$. This on its own is a fact worth remembering, and it may even be enough of a hint for you to easily remember this whole list!

Now, let's look at the sequence $12, 24, 36, 48\\.$ Notice that the second digit is always twice the first digit. And in fact, that pattern keeps going, *but*, while we have the numbers twenty-four, thirty-six, forty-eight, we *don't* have the numbers fifty-ten, sixty-12, seventy-fourteen, etc., so at that point, we need to perform addition, like so:

$$\begin{align}12&=(1\times10)+(1\times2)\\
24&=(2\times10)+(2\times2)\\
36&=(3\times10)+(3\times2)\\
\cdots\\
12m&=(m\times10)+(m\times2)
\end{align}$$

So now, even if you don't have the table memorized, you can quickly do the math in your head.
