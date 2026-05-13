---
name: game-ui-design
description: Design complete game UI screen systems, feature flows, screen inventories, UX specs, and implementation-ready interface briefs for games. Use when Codex is asked to design, extend, audit, or implement game UI for splash/login, lobby, HUD, battle, quests, inventory, heroes, growth, shop, gacha, events, guild, chat, mail, rankings, monetization, live-ops, onboarding, or other player-facing game screens.
---

# Game UI Design

## Overview

Use this skill to turn a game concept, existing screen, or partial UI category list into a coherent game UI system. Prioritize playable, screen-level design over marketing copy: define what the player sees, what they can do, how states change, and how the interface supports the game's core loop.

## Workflow

1. Extract the game context:
   - Genre and camera/play mode: RPG, card battler, shooter, simulation, casual puzzle, roguelike, strategy, MMO, sports, rhythm, etc.
   - Platform: mobile portrait, mobile landscape, PC, console, web, cross-platform.
   - Art direction: fantasy, sci-fi, cyberpunk, cozy, anime, realistic, minimalist, retro, etc.
   - Core loop: prepare, play, win/lose, collect, upgrade, socialize, return tomorrow.
   - Business and retention model: premium, free-to-play, battle pass, gacha, cosmetics, ads, live events.

2. Map the UI ecosystem:
   - Use `references/ui-screen-taxonomy.md` when the request needs a complete screen catalog or category expansion.
   - Group screens by player journey: first entry, core play, system management, social/live-ops, economy/monetization, progression, competitive, collection, creator/community, support/settings.
   - Mark each screen as `must-have`, `genre-specific`, or `optional`.

3. Choose the relevant screens:
   - Do not include every possible screen by default.
   - Select screens that support the user's stated genre, loop, platform, and monetization.
   - Add missing screens when the user has only named a few categories but clearly wants a full UI plan.

4. Specify each screen with this structure:
   - Screen purpose: what player problem it solves.
   - Entry points: where the player opens it from.
   - Primary actions: the 1-3 actions the screen must make easiest.
   - Layout: navigation, content hierarchy, resource/status zones, CTA placement.
   - Components: bars, tabs, lists, cards, grids, modals, HUD widgets, radial menus, minimaps, drawers.
   - States: loading, empty, locked, available, claimable, selected, insufficient resource, error, cooldown, completed.
   - Feedback: animation, sound, haptics, number change, reward reveal, confirmation.
   - Data needs: currencies, timers, player level, inventory count, stamina, progress, social status.
   - Edge cases: full inventory, network loss, expired event, duplicate reward, under-level player.

5. Design interaction quality:
   - Make repeated actions fast: one-tap claim, batch upgrade, presets, filters, sort, recent tabs, skip/auto where genre-appropriate.
   - Keep monetization legible: price, value, limits, probability disclosure, purchase confirmation, refund/support entry.
   - Keep competitive and reward screens trustworthy: ranking rules, settlement timing, score source, reward thresholds.
   - Keep live-ops visible without overwhelming core play: reserve limited high-priority entry points and rotate secondary events.

6. If implementing UI:
   - Build the actual playable/tool-like interface as the first screen, not a landing page.
   - Use the existing app's stack, components, assets, and visual conventions when working in a repo.
   - Prefer stable responsive dimensions for HUDs, boards, resource bars, cards, and toolbars so labels and dynamic values do not shift layout.
   - Verify desktop and mobile layouts when feasible, especially for dense HUDs, bottom navigation, modal stacking, and long localized text.

## Output Formats

For broad UI planning, provide:

```markdown
## UI Screen Map
| Category | Screen | Priority | Player Goal | Key Components | Main States |
|---|---|---|---|---|---|
```

For detailed screen design, provide:

```markdown
## Screen: <name>
- Purpose:
- Entry Points:
- Primary Actions:
- Layout:
- Components:
- States:
- Interactions:
- Visual/Motion Direction:
- Edge Cases:
```

For implementation handoff, include:

```markdown
## Component Inventory
| Component | Used In | Props/Data | States |
|---|---|---|---|

## Flow Notes
1. ...
```

## Quality Checklist

- Cover the full player journey from first launch to repeated daily return.
- Make every screen's primary action obvious within three seconds.
- Separate persistent HUD, temporary popups, and deep management screens.
- Include locked, empty, claimable, cooldown, and error states for systems that need them.
- Use genre-specific controls: skill wheels for action games, formation grids for tactics, deck panels for card games, timelines for narrative games, maps for exploration games.
- Avoid generic dashboard language when the game fantasy can carry the UI.
- Do not overload the main lobby with every event; prioritize by player value and urgency.
- Ensure reward, shop, gacha, and ranking screens communicate rules clearly.

## Resources

- `references/ui-screen-taxonomy.md`: load when expanding or auditing a game's complete UI screen set.
