---
layout: center
transition: fade-out
---

<SlidevVideo class="w-full rounded-lg" muted autoreset="click" loop autoplay v-motion :initial="{ y: -32 }">
  <source src="/assets/4/accolade.mp4" type="video/mp4" />
</SlidevVideo>
<div class="absolute inset-0 flex justify-center items-center">
<div class="border-2 border-white w-28 h-12 mr-57 mt-2 rounded-lg border-dashed">
</div>
</div>
<div
  class="absolute"
  v-motion
  :initial="{ y: -32 }"
>
  <div>

[Accolades]{class="text-yellow font-bold"} are rewards for doing specific actions in the game

They are worth small amount of XP points at the end of the match

  </div>
</div>

<!--
Accolades are a sub-elements of the points popup and their task is almost exclusively motivating the player up even more.
Sometimes it even displays multiple accolades for one action as shown here.

For example "Flight dispatcher" accolade shown here

is given to a player who eliminates enemy pilot without destroying the aircraft itself.
-->