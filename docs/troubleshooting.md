# Troubleshooting

## `/swipe:swipe` isn't listed

Start a new Claude Code session after installing. If it's still missing, run `/plugin` and check that `swipe` is installed and enabled.

Plugin commands include the plugin name, so the full command is `/swipe:swipe`.

## Claude says it can't publish the page

Publishing needs a session signed in with `/login` on a Pro, Max, Ultra, Team or Enterprise plan. API key, Bedrock and Vertex sessions can't publish artifacts. On Team and Enterprise, an owner may have turned artifacts off.

## Claude says the artifact tools aren't available

`/swipe:swipe` only works in an interactive session. `claude -p` doesn't have the artifact tools it needs.

## The page says to open it in Claude while signed in

Open the link while signed in to the same claude.ai account you use with Claude Code. Only that account can read or change the page.

## The page shows "No cards waiting"

The page is ready, but it has nothing for you yet. Leave it open and cards will land there, or check that Claude has finished preparing them.

## The cooking screen doesn't go away

Check the terminal, as Claude may be waiting for a permission or still working. If Claude stopped, run `/swipe:swipe` again. The cooking screen gives up on its own after 10 minutes.

## I see a deck I didn't expect

Every chat shares one page, so several decks can wait at once. Each chat only reads the answers to its own deck. Unfinished decks stay on the picker for now, and there's no way to dismiss them yet.

## Swiping doesn't work

Use the buttons under the card, which do the same thing. On a card too long to fit, dragging up and down scrolls it, so use the "u decide" button instead of swiping up. Please also report your phone model and app in a [beta feedback issue](https://github.com/tunmin11/swipe-deck/issues/new?template=beta-feedback.md).

## Claude didn't continue after I locked in

Tell Claude you're done, and it will check straight away. Claude stops checking on its own after 15 minutes, and it can't check if the session has been closed. If it's waiting for a permission in the terminal, approve it there.

## Claude keeps using a deleted page

Delete `~/.claude/swipe-deck-url`, then run `/swipe:swipe` again. Claude will publish a new page.

## Getting a newer version

```bash
claude plugin update swipe@swipe-deck
```

Then start a new session. Claude updates your existing page the next time you run `/swipe:swipe`, and the link stays the same.

## Removing it

```bash
claude plugin uninstall swipe@swipe-deck
rm ~/.claude/swipe-deck-url
```

Then delete the Swipe Deck page from your artifacts at [claude.ai/code/artifacts](https://claude.ai/code/artifacts), which also erases your stored cards and answers.
