redis.sunfish.lua
=================

Tiny and basic chess engine for lua, enabled for running as Lua script in the Redis database.

- Redis port of https://github.com/soumith/sunfish.lua 
- Which is a Port of https://github.com/thomasahle/sunfish

## Usage

![alt text](redis-chess.gif)

```bash
sunfish.lua git:(master) ✗ redis-cli -x script load < sunfish.lua
"30d00b1eee6b536de87503593446e879578d31e2"
➜  sunfish.lua git:(master) ✗ redis-cli
127.0.0.1:6379> evalsha 30d00b1eee6b536de87503593446e879578d31e2 0
 1) "                  "
 2) "                  "
 3) "  r n b q k b n r "
 4) "  p p p p p p p p "
 5) "  . . . . . . . . "
 6) "  . . . . . . . . "
 7) "  . . . . . . . . "
 8) "  . . . . . . . . "
 9) "  P P P P P P P P "
10) "  R N B Q K B N R "
11) "                  "
12) "                    "
13) "your move: "
127.0.0.1:6379> evalsha 30d00b1eee6b536de87503593446e879578d31e2 0 e2e4
 1) "                  "
 2) "                  "
 3) "  r n b q k b . r "
 4) "  p p p p p p p p "
 5) "  . . . . . n . . "
 6) "  . . . . . . . . "
 7) "  . . . . P . . . "
 8) "  . . . . . . . . "
 9) "  P P P P . P P P "
10) "  R N B Q K B N R "
11) "                  "
12) "                    "
13) "your move: "
(1.52s)
127.0.0.1:6379> evalsha 30d00b1eee6b536de87503593446e879578d31e2 0 d2d3
 1) "                  "
 2) "                  "
 3) "  r . b q k b . r "
 4) "  p p p p p p p p "
 5) "  . . n . . n . . "
 6) "  . . . . . . . . "
 7) "  . . . . P . . . "
 8) "  . . . P . . . . "
 9) "  P P P . . P P P "
10) "  R N B Q K B N R "
11) "                  "
12) "                    "
13) "your move: "
(2.39s)

```
