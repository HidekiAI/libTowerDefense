# libTowerDefense - Tower Defense (lib) demo

My C++ practice to refresh on C++17

## Key points and goals

Key to point out is that it will be attempted with least amount to C-libs
(i.e. sprintf, printf, etc) as possible (there may be places that are inevitable)
due to importing of 'extern C' libs.  Avoidance when possible of usage of
new/delete, but when needed, will opt towards strict RAII ownerships as
well as usages of `unique_ptr<T>` and such, to avoid memory problems such as
double-deletes, delete array as element, and so on.

Where possible, templates will be utilized rather than inheritances and polymorphisms,
as well as avoidance of dynamic (up and down) casting.

Challenges to such goals would probably require some thoughts, for example, there are
clever implementations in ProtoBuf-grpc in which the demo/sample uses `void *` address
as an unique tag for identifying messages on async-callbacks.  Clever as it may be in
the ideal world, in practice, that `void *` when recasted, may no longer be accessible
in real world...  So it will be interesting to see what other smart people have done
and learn from them.

## Info


view-less (as in, control-model-view) library for tower defense to be used either as remote (server mode, including localhost loopbacks and named pipe), or local (statically linked async or blocking), agnostic of time passed sinced last call (untied from framerate)

## Why lib?

Idea is trivial (yet it may be a bit ambitious), to have it as a lib so that it can either reside on standalone client or on server independant from view, concentrating only on simulation part.  Collision is again, viewless because the map is grid/cell based and whatever entity resides on that cell are assumed to be the attacker or defender.  This also makes it easier to manage pathfinding of A.I. attackers to just follow the (grid-based) waypoints as its rails (possibly be easy to dynamically regenerate waypoints dynamically for free-to-place open maps as well).

Data model at the moment is quad for simplicity of finding its adjacent neighbors of 2-dimensional grid, but care will be taken to handle hexagons.

## Status

Please note, this is W.I.P. and I only have repos on my local repos-server, will upload/push here when I get a separate View mode done in ASCII (yes, I like ASCII graphics)
