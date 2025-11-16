---
layout: center
clicks: 10
---

<div
  v-motion
  :initial="{ y: 0, x: 0, }"
  :click-3="{ y: -64, x: 0, transition: { type: 'tween'}}"
  :click-6="{ y: 0, x: 0, transition: { type: 'tween'}}"
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

This number grows to [12 indicators]{class="bg-gradient-to-r from-purple-600 via-amber-500 to-sky-600 bg-clip-text text-transparent font-bold"} if we count duplicated information

  </div>
</div>
</div>

<div v-click="10" class="absolute inset-0 flex justify-center items-center">
<div class="border-2 border-sky w-48 h-20 mr-64 mt-28 rounded-lg border-dashed">
</div>
</div>

<Arrows />

<!--
I want to show you example of 3 UI elements present in recently released Battlefield 6.

Why? First person shooter are a perfect example of simple UIs because those aren't the main focus.
Also that's all I've been playing since it came out a month ago so yeah.

In FPS games it's more important what happens behind the UI, so the interface needs to unobtrusive for the player yet still do its job of communicating game state.
```
click=1
```
Here we have a clip of a conquest game mode match.

Where we need to capture and hold flags to make other team lose tickets.

Each teams start with 1000 tickets each. First team that reaches 0 tickets loses.

The gameplay is rather chaotic so the UI needs to be simple and easy to read at a glance.
```
click=2
```
Let's go to the first UI element I will be talking:

```
click=3
```
The objectives interface.

This element is present throughout the entire match and shows the ticket count for both teams as well as the status of each flag.

If you take a glance at it it's rather simple and minimalistic. BUT
```
click=4
```
If you look a bit closer you can see that it actually communicates quite a lot of information to the user.

To be exact I counted 7 unique indicators here:

But since this element has a lot of small variants the overall number in the game would probably be even higher.
```
click=5
```
If we count duplicates the number grows to 12 indicators.

The main problem of this interface is that unless you are familiar with the game and understand the mechanics this interface tells you almost nothing.

But that is not it's responsibility. The game uses other forms of educating the player about the mechanics. During loading screen or through dedicated tutorials

Web counterpart would be something like a header on Allegro's page.

This element is simple, relatively static since it follows you everywhere yet communicates a lot of information about the state of the website (like cart status, authentication status, notifications etc.)

It also heavily relies on users being familiar with common web conventions to understand what is going on.

```
click=6
```
Moving to something entirely different.

```
click=7
```
This... I don't know what to call it.

Abilities progression UI?

```
click=8
```
This element shows very little information when compared to the previous one.

Simply your current ability level and occasional notifications about new levels unlocked.

But it also directly educates player what his new ability does. That popup also acts as an indicator that you leveled up.

Pretty clever if you ask me.

```
click=9
```
For the next element I won't zoom in since it is important to see it in context of the whole screen.
```
click=10
```
I'm talking about this element - the score popup.

This element is a weird one because it shows information that isn't really important during the gameplay.

We don't really need to know precise number of points we've just earned.
Same as we don't need to know the type of action we are currently performing. (I'm talking about those rectangles with "Defending", "Defensive" etc.)

But that is also by design. This element is meant as some sort of hype generating device.

When you perform a good action you get rewarded with points and that popup.

The better you do the more chaotic this element gets.
-->
