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
