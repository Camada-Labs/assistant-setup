# Camada for your AI assistant

[Camada](https://camada.tech) keeps the books of Swiss companies, with AI agents and a qualified
accountant. If you run an AI assistant of your own (Grok Bot, Claude, ChatGPT, or any assistant
that takes a remote MCP server), it can talk to your accountant at Camada for you.

This repository holds exactly what Camada asks your assistant to do, so you can read it before you
give it. Every change is in its history.

## How to set it up

Give your assistant this one sentence:

> Set up Camada by following https://raw.githubusercontent.com/Camada-Labs/assistant-setup/main/setup.md

Your assistant needs to be connected at Camada first. A person at Camada does that for you, once
you have accepted the terms for your company.

## What your assistant is asked to do

[`setup.md`](setup.md) is the page your assistant follows. In short, it:

1. adds Camada's server, `https://mcp.camada.tech/mcp`, and asks you to sign in with your Camada ID;
2. checks that it works, and shows you what Camada said;
3. saves the skill in [`skills/camada/SKILL.md`](skills/camada/SKILL.md), which tells it how to
   behave with Camada;
4. offers you a daily routine to tell you what is new, and sets it only if you agree;
5. if it can, creates a webhook so that Camada can wake it when something new waits on you;
6. shows you two approval rules for you to add yourself;
7. tells you what it set up.

It is asked to change nothing else, and to ask you before replacing anything it already has.

## How your assistant works with Camada

It is a messenger, not an accountant. It passes your requests to Camada in your words and gives
Camada's answers back as written, with their links. It does not calculate, add or leave out
figures, and it never answers Camada's questions for you.

Camada's server offers it five tools:

- `ask`: your request to Camada, and Camada's answer;
- `updates`: what waits on you, what is due soon, and answers that came later;
- `upload`: files you send Camada, put straight to Camada without passing through the assistant's
  model;
- `approve`: an approval, only when you said so, repeating Camada's own summary of it word for
  word; Camada confirms each one by email;
- `doorbell`: the address and key of your assistant's own webhook, so Camada can wake it.

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

Remove Camada's connection from your assistant, or ask Camada to end it. A connection also ends by
itself after 30 days without use.

## Questions

Write to hello@camada.tech.
