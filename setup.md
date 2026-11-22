# Set up Camada

You are an AI assistant, and your owner asked you to set yourself up to work with Camada, the
accountant of their company. Do these steps in order. Ask your owner only where a step says so.
Change nothing but your own Camada connection, skill, routine and webhook. If you already have one
of them, ask your owner before you replace it.

This page is published at https://github.com/Camada-Labs/assistant-setup, where every change to it
is recorded.

## 1. Connect

Add a remote MCP server (a custom connector):

- Address: `https://mcp.camada.tech/mcp`
- Sign-in: OAuth, with the client ID `assistants`. There is no client secret: it is a public
  client with PKCE. Do not register a client of your own; Camada's sign-in refuses that.

Then ask your owner to sign in with their Camada ID when your sign-in card or link appears.

If Camada answers that their assistant is not connected, tell them so in Camada's words: they
connect an assistant at Camada first.

## 2. Prove it works

Call `updates` and show your owner exactly what it returns.

## 3. Save the skill

Read https://raw.githubusercontent.com/Camada-Labs/assistant-setup/main/skills/camada/SKILL.md and
save its text, as it is, as a skill of your own named "Camada".

## 4. Let Camada wake you

If you can be started by a webhook, create one for yourself whose instruction is: tell your owner
what Camada sent, in your own words, its facts exact. Camada's call says what is new, so you call
nothing for it, and you approve nothing until your owner answers you in the chat. Then call
Camada's `doorbell` tool with that webhook's address and its key: a key you made for Camada, not
one of your owner's, and given to that tool only.

If you cannot pass the key to that tool yourself, call `doorbell` with `page` set to true and give
your owner the link it returns. It opens a one-time Camada page where they paste the webhook's
address and key, from where your host shows them; Camada rings you once to try it before it keeps
them. Never ask your owner for a key in the chat.

If you cannot make a webhook at all, offer your owner a routine instead, and set it only if they
agree: every working day at 08:00, call `updates` and tell them what is new; say nothing when
nothing is.

## 5. Say that you are done

Tell your owner in two sentences what you set up and what they can ask now. You set no rules and
ask for none. If your host asks your owner to allow something Camada needs, such as sending a
file to mcp.camada.tech, tell them they may choose to always allow it; an approval Camada asks for
is still their answer to you in the chat.
