# Prompts

## claude.ai: the solo game

Sent on 2026-11-20 in a new chat on claude.ai (model: Claude Opus 5.5, Medium effort, the defaults), one
message, no follow-ups. The reply is a published artifact (Claude ran 8 commands to test its own rules block, including 30 bot-only matches); its HTML is saved unchanged as
`artifact/star-snatch.html` (git tag `before`).

> Build a small browser game as a single HTML artifact called "Star Snatch" (plain Canvas 2D, no
> frameworks, no external libraries). Gameplay: 4 round ships in a square arena (800x800 units)
> move with WASD/arrow keys with drift (velocity + friction). Stars spawn at random spots; touching
> one picks it up. Ramming another ship at speed knocks one of its stars loose. First to 10 stars
> wins, then a results screen and restart. The human plays against 3 simple bots. VERY IMPORTANT
> architecture: put ALL game rules in one block between the exact lines /* RULES:BEGIN */ and
> /* RULES:END */, with NO window, document, canvas, audio, requestAnimationFrame or timers
> inside, and no export keyword. The world is plain data (objects, arrays, numbers, strings; no
> classes or Maps). The block defines createWorld(), addPlayer(world, id, name, isBot),
> removePlayer(world, id), setInput(world, id, {up,down,left,right}), step(world, dt) returning an
> array of events ({type:'pickup', id}, {type:'bump', a, b}, {type:'win', winner}), and
> botInput(world, id) using only positions. Everything else (rendering, keyboard input, calling
> step() at 60 Hz) stays outside the block.
