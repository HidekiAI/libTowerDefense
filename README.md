# libTowerDefense
view-less (of the C.M.V.) library for tower defense

## Why lib?

Idea is trivial (yet it may be a bit ambitious), to have it as a lib so that it can either reside on standalone client or on server independant from view, concentrating only on simulation part.  Collision is again, viewless because the map is grid/cell based and whatever entity resides on that cell are assumed to be the attacker or defender.  This also makes it easier to manage pathfinding of A.I. attackers to just follow the (grid-based) waypoints as its rails (possibly be easy to dynamically regenerate waypoints dynamically for free-to-place open maps as well).

Data model at the moment is quad for simplicity of finding its adjacent neighbors of 2-dimensional grid, but care will be taken to handle hexagons.

## Status

Please note, this is W.I.P. and I only have repos on my local repos-server, will upload/push here when I get a separate View mode done in ASCII (yes, I like ASCII graphics)
