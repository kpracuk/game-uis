---
layout: center
clicks: 11
transition: fade-out
---

<div
  v-motion
  :initial="{ y: 0, x: 0, }"
  :click-3="{ y: -64, x: 0, transition: { type: 'tween'}}"
  :click-6="{ y: -32, x: 0, transition: { type: 'tween'}}"
  :click-7="{ y: 0, x: 0, transition: { type: 'tween'}}"
>
  <Conquest :clicks="$clicks" />
</div>
<div class="relative w-full">
<div
  v-click="[3, 4]"
  class="absolute w-full text-center"
  v-motion
  :initial="{ opacity: 0, y: 0, x: 0, }"
  :click-3="{ opacity: 1, y: -64, x: 0, transition: { type: 'tween'}}"
>
  <div>

  [OBJECTIVES INTERFACE]{class="text-sky-400 font-bold"}

  Example of relatively static but information-dense UI element

  </div>
</div>
<div
  v-click="[4, 6]"
  class="absolute"
  v-motion
  :initial="{ opacity: 0, y: 0, x: 0, }"
  :click-4="{ opacity: 1, y: -64, x: 0, transition: { type: 'tween'}}"
>
  <div>

This UI element has [7 unique indicators]{class="text-yellow font-bold"} communicating game state

  </div>
<div v-click="5">

This number grows to [12 indicators]{class="bg-gradient-to-r from-red-600 to-sky-600 bg-clip-text text-transparent font-bold"} if we count duplicated information

  </div>
</div>

<div
  class="absolute w-full"
  v-click="[6, 7]"
  v-motion
  :initial="{ opacity: 0, y: 0, x: 0, }"
  :click-6="{ opacity: 1, y: -16, x: 0, transition: { type: 'tween'}}"
>
  <img src="/assets/3/header.png" class="rounded-lg">
</div>

</div>

<div v-click="11" class="absolute inset-0 flex justify-center items-center">
<div class="border-2 border-sky w-48 h-20 mr-64 mt-28 rounded-lg border-dashed">
</div>
</div>

<Arrows />

<!--
I will use examples from recently released Battlefield 6.

Why? Because that's all I've been playing since it came out a month ago
But mainly because first person shooter are a perfect example of simple and easy to understand UIs because the interface is not the main focus.

In FPS games it's more important what happens behind the UI, so the interface needs to unobtrusive for the player yet still do its job of communicating game state.
```
click=1
```
Here we have a clip of a conquest game mode match.

For those who haven't played Battlefield games before.

We need to capture and hold flags to make the other team lose tickets.

Each teams start with 1000 tickets. First team that reaches 0 tickets loses.

Gameplay can get pretty chaotic so the UI needs to be simple and easy to read at a glance.
```
click=2
```
Let's go to the first UI element I will be talking about:

```
click=3
```
The objectives interface.

This element is present throughout the entire match and mainly shows the ticket count for both teams and the status of each flag.

If you take a glance at it it's rather simple and minimalistic. BUT
```
click=4
```
If you look a bit closer you can see that it actually communicates quite a lot of information to the user.

To be exact I counted 7 unique indicators here:

Those are just the ones present in this specific moment. Overall throughout the match there are more indicators that can appear here. But those are rather very contextual.
```
click=5
```
If we count duplicates the number grows to 12 indicators.

The main problem of this interface is that unless you are familiar with the game and understand the mechanics this interface tells you almost nothing.

But the saving factor is that it's not the responsibility of this element. The game uses other forms of educating the player about the mechanics. During loading screen or through dedicated tutorials

```
click=6
```

Closest web counterpart I could think of would be something like a header on Allegro's page.

This element is simple yet communicates a lot of information about the state of the website (like cart status, authentication status, notifications etc.)

It is also relatively static and follows you everywhere on the platform. 

It also heavily relies on users being familiar with common web conventions to understand what is going on.

```
click=7
```
Moving on to an element that is pretty much the opposite.

```
click=8
```
This... I don't know what to call it.

Abilities progression UI?

Simply it shows you your current ability level and occasional notification about a level up.

```
click=9
```
This element shows very little information when compared to the previous one.

But it also directly educates player what his new ability does.

While it does not directly say something like "You've unlocked new ability" just the presence of the edu tip is enough to suggest that.

Pretty clever if you ask me.

```
click=10
```
For the next element I won't zoom in since it is important to see it in context of the whole screen.
```
click=11
```
I'm talking about this element - the score popup.

This element is a weird one because I was just glazing how so minimalistic and simple game UIs are. And this one seems to suggest otherwise

We don't really need to know precise number of points we've just earned.
Same as we don't need to know the type of action we are currently performing. We already know that

(I'm talking about those rectangles with "Defending", "Defensive" etc.)

But believe it or not that is also by design. This element is meant as some sort of hype generating device.

The better you do the more chaotic this element gets and more points are displayed.

As a bonus one - we will talk about one of it's the sub-elements
-->
