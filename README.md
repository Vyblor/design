# Vyblor design skill

Design judgement for coding agents, so that what they build stops looking machine-made: how to decide type, colour, space, composition, motion, Korean typography, copy and states, and what to do instead of the habits that give AI output away.

```sh
npx skills add vyblor/design
```

Then ask your agent for something, for example `vyblor 스킬로 랜딩 페이지 만들어 줘` or "use the vyblor skill and build a landing page".

## What this is

Plain text. There are no scripts, no install hooks and no telemetry, and it needs no account. It holds judgement only.

The pieces themselves (components, motion and full pages) are in the [Vyblor](https://vyblor.com) library, which an agent reaches through the signed-in MCP server or the `vyblor` CLI. The skill says when to use them, and it works without them.

## Files

- `skills/vyblor/SKILL.md`: the steps an agent follows
- `skills/vyblor/references/`: type, colour, space, motion, Korean, states, copy and how to use the library

## Licence

The skill text is under the [MIT licence](LICENSE). The Vyblor library, its pieces, its name and its logo are not part of this repository and are not covered by that licence.
