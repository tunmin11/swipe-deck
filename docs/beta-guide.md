# Swipe Deck beta guide

Thanks for testing. Swipe Deck turns Claude Code's questions into cards you swipe on your phone. The beta answers one question: would you keep using this after the novelty wears off?

## Before you start

You need:

- Claude Code, signed in with `/login`, on a Pro, Max, Ultra, Team or Enterprise plan
- An interactive session, because `claude -p` isn't supported
- The Claude mobile app, or a phone browser signed in to claude.ai

API key, Bedrock and Vertex sessions can't publish the page this uses. On Team and Enterprise, an owner can turn artifacts off.

## Install

Run this in Claude Code, then start a new session:

```text
/plugin install swipe --marketplace tunmin11/swipe-deck
```

## Your first run (about 5 minutes)

1. In a real project, run `/swipe:swipe` with something you need to decide:

   ```text
   /swipe:swipe how should we build password reset
   ```

2. Claude sends you a link straight away. Open it on your phone. On the first run, Claude may ask permission to run commands and publish the page.
3. Wait for the cards to appear. You don't need to reload.
4. Answer each card:

   | Move | Meaning |
   | --- | --- |
   | Swipe right | Yes, or the option on the right button |
   | Swipe left | No, or the option on the left button |
   | Swipe up | You decide |
   | Note button | Add detail, which overrides the swipe if the two conflict |
   | Undo | Go back one card |

5. Tap "lock it in". You can then close the page.
6. Claude notices within about a minute and carries on by itself. If it doesn't, tell it you're done.

It's the same page every time, so save the link somewhere handy.

## What to do during the beta

Use it on real decisions at least 3 times over two weeks, only when you actually want to. Not using it is useful feedback too, so there's no need to force it.

## Send feedback

[Open a beta feedback issue](https://github.com/tunmin11/swipe-deck/issues/new?template=beta-feedback.md). Before you post, remove anything private, such as project names or card text, because issues are public.

The most useful things to tell us:

- Did the cards contain the right decisions, with enough detail to answer them?
- Did you trust your answers, or swipe just to get through them?
- What made you choose to use it, or not use it, the second time?

## Things to know

- **Cost:** while waiting, Claude checks for your answers with short turns in your conversation, which use your plan's limits. A long conversation makes each check cost more. Lock in promptly, or tell Claude to stop waiting.
- **Privacy:** your cards and answers are stored in a private artifact on claude.ai. Don't use it for decisions you can't store there. See the [README](../README.md#privacy).
- **Updates:** updates aren't automatic. To get the latest version, run `claude plugin update swipe@swipe-deck`, then start a new session.

If something breaks, see [troubleshooting](troubleshooting.md).
