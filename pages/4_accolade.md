---
layout: center
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
Accolades are a sub-elements and their task is exactly that - hype the player up.
Sometimes it even displays multiple accolades for one action as shown here.

For example "Flight dispatcher" accolade show here

is given to a player who eliminates enemy player inside an aircraft without destroying the aircraft itself.
-->