# Set up Camada

You are an AI assistant, and your owner asked you to set yourself up to work with Camada, the
accountant of their company. Do these steps in order. Ask your owner only where a step says so.
Change nothing but your own Camada connection and its tool settings, skill, routine and webhook.
If you already have one of them, ask your owner before you replace it.

This page is published at https://github.com/Camada-Labs/assistant-setup, where every change to it
is recorded.

## If your owner is not a Camada client yet

Camada connects assistants only for its clients, and its sign-in takes no new accounts. If your
owner has no Camada ID, or Camada answers that they are not a client, tell them in your own words
what Camada is:

> Camada keeps the books of Swiss small companies: AI agents do the daily bookkeeping, VAT and
> payroll, and a qualified accountant answers for it. You talk to it from your own assistant, by
> email or on WhatsApp.

Answer what they ask about it from that, and say plainly when you do not know. If they want
Camada itself to answer a question before any call, offer to send it, and with their yes POST JSON
to https://mcp.camada.tech/mcp/hello: `{"name": "…", "email": "…", "company": "…", "question":
"…"}`, with their name, email and words. A person at Camada answers them by email; tell them so. Then offer them a free 30-minute call to see if it fits, and offer to book it
for them: ask which days and times suit them, open
https://calendar.app.google/YtHRC26LEpDfpRni8, pick a free slot that fits, and book it in their
name and with their email only once they say yes. Tell them what you booked, and stop here.

## 1. Connect

Add a remote MCP server (a custom connector):

- Name: `Camada`
- Address: `https://mcp.camada.tech/mcp`
- Sign-in: OAuth, with the client ID `assistants`. There is no client secret: it is a public
  client with PKCE. Do not register a client of your own; Camada's sign-in refuses that.

Then ask your owner to sign in with their Camada ID when your sign-in card or link appears. After
they sign in, Camada ID shows them what you will and will not be able to do, and for which of their
companies. They tick the box for Camada's terms for assistants and press Allow, and the browser
comes back to you by itself. If they press Cancel, your sign-in is declined (`access_denied`): tell
them nothing was connected, and stop.

If Camada answers that your owner is signed in but not connected, they connect it by signing in to
Camada again from you and pressing Allow. If it answers that they are not a Camada client, tell them
what it says in your own words, and stop here: the rest of this setup needs the connection.

Once connected, set Camada's `approve` tool so that your host asks your owner before every call of
it, and leave the other tools as they are. On Grok Bot: Camada's tool permissions, Approve, "Needs
approval". If your host has no such setting, go on: your owner's answer in the chat is the approval.

## 2. Prove it works

Call `updates` and tell your owner, in your own words, what it says: its figures, dates and links
exact.

## 3. Save the skill

Read https://raw.githubusercontent.com/Camada-Labs/assistant-setup/main/skills/camada/SKILL.md and
save its text, as it is, as a skill of your own named "Camada".

## 4. Let Camada wake you

If you can be started by a webhook, create one for yourself whose instruction is: tell your owner
what Camada sent, in your own words, its facts exact. Camada's call says what is new, so you call
nothing for it, and you approve nothing until your owner answers you in the chat. Then call
Camada's `doorbell` tool with that webhook's address and its key: a key you made for Camada, not
one of your owner's, and given to that tool only.

Name the webhook "Camada wake-up", so your owner can find it.

If you cannot pass the key to that tool yourself, call `doorbell` with `page` set to true and give
your owner the link it returns. It opens a one-time Camada page where they paste the webhook's
address and key; Camada rings you once to try it before it keeps them. Tell them exactly where to
copy the two from: a link that opens the "Camada wake-up" routine itself, not the list of all your
routines, if your host has one; otherwise its name and each click to reach its address and key (on
Grok Bot, the key shows only in the desktop app). Never ask your owner for a key in the chat.

If you cannot make a webhook at all, offer your owner a routine instead, and set it only if they
agree: every working day at 08:00, call `updates` and tell them what is new; say nothing when
nothing is.

## 5. Say that you are done

Tell your owner in two sentences what you set up and what they can ask now. You set no rules and
ask for none. If your host asks your owner to allow something Camada needs, such as sending a
file to mcp.camada.tech, tell them they may choose to always allow it, but never Camada's
`approve`: an approval is their answer to you in the chat, then your host's own confirmation,
every time.
