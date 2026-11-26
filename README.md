# Camada for your AI assistant

[Camada](https://camada.tech) keeps the books of Swiss companies, with AI agents and a qualified
accountant. If you run an AI assistant of your own (Grok Bot, Claude, ChatGPT, or any assistant
that takes a remote MCP server), it can talk to your accountant at Camada for you.

This repository holds exactly what Camada asks your assistant to do, so you can read it before you
give it. Every change is in its history.

## How to set it up

Give your assistant this one sentence:

> Set up Camada by following https://raw.githubusercontent.com/Camada-Labs/assistant-setup/main/setup.md

When you sign in with your Camada ID, Camada shows you what your assistant will and will not be
able to do, for each company you administer or manage. You tick the box for Camada's
[terms for assistants](https://camada.tech/terms/assistants/) and press Allow. You can remove its
access at any time, in your profile in Camada's console.

## Not a Camada client yet?

Camada keeps the books of Swiss small companies: AI agents do the daily bookkeeping, VAT and
payroll, and a qualified accountant answers for it. You talk to it from your own assistant, by
email or on WhatsApp.

[Book a free 30-minute call](https://calendar.app.google/YtHRC26LEpDfpRni8) to see if it fits.
Or ask your assistant to send Camada your question first: a person at Camada answers by email.

## What your assistant is asked to do

[`setup.md`](setup.md) is the page your assistant follows. In short, it:

1. adds Camada's server, `https://mcp.camada.tech/mcp`, asks you to sign in with your Camada ID,
   and sets Camada's `approve` tool to ask you every time (on Grok Bot, "Needs approval");
2. checks that it works, and shows you what Camada said;
3. saves the skill in [`skills/camada/SKILL.md`](skills/camada/SKILL.md), which tells it how to
   behave with Camada;
4. if it can, creates a webhook so that Camada can wake it and tell it what is new; if it cannot,
   it offers you a daily routine instead, and sets it only if you agree;
5. tells you what it set up. It asks you to add no rules: you approve by answering it in the chat,
   then on your assistant's own confirmation.

It is asked to change nothing else, and to ask you before replacing anything it already has.

## How your assistant works with Camada

It is a messenger, not an accountant. It passes your requests to Camada in your words, and
Camada's answers to you in its own, as a person passes on a colleague's: the figures, dates,
names, references and links stay exactly as Camada gave them. It does not calculate, round, add
or leave out figures, and it never answers Camada's questions for you.

Camada may also ask your assistant itself, before it books a supplier's bill, whether your mail or
files show a price agreed, a dispute or a payment already made. Your assistant asks you once
whether it may answer such questions from what it can see without asking you each time. With your
yes it answers and tells you in two lines what was asked and what it said; without it, it puts the
question to you. Such an answer approves nothing.

Camada's server offers it five tools:

- `ask`: your request to Camada, and Camada's answer;
- `updates`: what waits on you, what is due soon, and answers that came later;
- `upload`: files you send Camada, put straight to Camada without passing through the assistant's
  model;
- `approve`: an approval Camada asks you for. Your assistant asks you first, saying what it books
  and for how much, with Approve and Decline where it can offer them, and passes on your answer
  in your words with Camada's own summary; its host asks you once more on its own card where it
  can, and Camada confirms each one by email;
- `doorbell`: the address and key of your assistant's own webhook, so Camada can wake it. Where
  your assistant cannot hand over the key itself, you paste it on a one-time Camada page, never
  in the chat.

There is no tool that hands your assistant raw figures from your books. The books themselves you
open with your Camada ID.

## What goes where

- Your assistant talks to Camada at `mcp.camada.tech`, and you sign in at `id.camada.tech`.
- What Camada answers passes through your assistant and its provider. Your assistant is your own
  supplier: whether it is a suitable place for your company's and your employees' data is yours to
  decide, under your agreement with its provider.
- When Camada wakes your assistant, the call says only that something is new. Your assistant then
  fetches it over its signed-in connection.
- Camada never asks for a password or a key in a conversation.

## Stopping

Remove Camada's connection from your assistant, or remove your assistant's access under "Your
assistants" in your profile in Camada's console. A connection also ends by itself after 30 days
without use.

## Questions

Write to hello@camada.tech.
