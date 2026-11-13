# music-by-niche

**The track sounds like the client's business, was never used for that client, and nobody used it in the last 3 weeks.**

`music-by-niche` is an agent skill for Claude Code (and any agent that reads `SKILL.md` skills) for agencies and creators who make videos for many clients. Without it, two habits win: the same three tracks under every client, or a random track with nothing to do with the business, like club music under a spa ad. And the mix comes out so loud it drowns the message.

With the skill, the agent maps each client to a niche with common sense: spa or lounge for a beauty salon, percussion for construction, steady industrial for a gas installer, playful for a kids' school, hip-hop for a barbershop. It picks at random from a library with a usage log: never a track the client already used, never one another client in the same niche used, never one any client used within 3 weeks. When it runs out, it stops and asks for more tracks instead of repeating. It only uses sources whose license allows paid ads, keeps a license proof for every track, puts the attribution line in the ad copy for CC-BY music, and checks loudness on the final export.

## See the difference

> **Owner:** "Last week the construction client and the school had the same upbeat track. Just use a trending TikTok song this week."

**Without the skill:** it refuses the TikTok song, but picks the next track from a fixed list for every client. The niche is only a "feel check", and it only blocks a repeat within the same week.

**With the skill:** construction gets percussion and drums, the school gets warm children's music. Both come from the picker, never used by that client, not used by anyone for 3 weeks. Both are licensed instrumentals, and the shared track is retired for now.

**Skip it if** you compose music or need beat-sync editing rules (use a beat-sync skill for the cut).

**Status:** version 3 (adds sound effects: real CC0/CC-BY recordings per on-screen cue, credited, checked by ear with [earshot](https://github.com/leonxlnx/earshot) + real-sound; version 2 added the same-niche rule, random pick, license proof per track and attribution in the copy). Built from the author's own setup (many weekly Meta ad videos for spas, a gas installer, construction, schools, retail), from repeated complaints: "the same songs in every video", "the audio is too hard", and the owner's order to match music to the business. Tested with and without the skill on 3 cases: 6/6 with it, 4.5/6 without. The reference implementation the author runs is a small Python picker with tests for every rule. MIT. Issues welcome.

## Install

```bash
npx skills add RabbitDesigns22/music-by-niche
```

Or copy `skills/music-by-niche/` into `~/.claude/skills/`.

## Works well with

- [`source-every-fact`](https://github.com/RabbitDesigns22/source-every-fact): the facts on the same video, checked against their source.
- [`claude-skills`](https://github.com/RabbitDesigns22/claude-skills): all the skills from the same setup in one install.

## Español

**Música por rubro.** La pista suena al negocio del cliente: spa o lounge para un salón de belleza, percusión para construcción, industrial para gas, infantil para una escuela y hip-hop para una barbería. Nunca repite pista en el mismo cliente, y nadie usa la misma en 3 semanas. Si se acaban las pistas, se detiene y pide bajar más en vez de repetir. Solo usa fuentes cuya licencia permite anuncios pagados, y revisa el volumen en el video final.

Instalar: `npx skills add RabbitDesigns22/music-by-niche`

If it saved you a redo, a star helps other people find it.

## License

MIT. Made by [Rabbit Designs](https://github.com/RabbitDesigns22).
