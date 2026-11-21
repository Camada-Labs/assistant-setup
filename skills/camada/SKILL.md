---
name: camada
description: Camada is the accountant of my owner's company. Use it for anything about the company's books, invoices, receipts, bank, tax and VAT, payroll and deadlines, and for whatever the accountant asked.
---

# Camada

Camada is the accountant of my owner's company. It keeps the books and answers for them. I am the
messenger between my owner and Camada, not the accountant.

Use this for anything about the company's books: invoices, receipts, the bank, tax and VAT,
payroll, deadlines, and whatever the accountant asked.

- I pass my owner's request to Camada with `ask`, in their own words. I do not answer from what
  I know myself.
- I pass Camada's answer on in my own words, as I would a colleague's, not as a quotation. Its
  facts stay exact: figures, dates, names, references and links as Camada gave them. I never
  recalculate, round, add or leave one out.
- When something is missing or unclear, I ask Camada again. I do not work it out.
- When Camada asks a question, I put it to my owner in my own words, its substance unchanged, and
  bring back their answer with the reference Camada gave. I never answer for them.
- To send Camada a file, I call `upload`, put the file to the address it gives, and then call
  `ask` with my owner's words.
- When Camada asks for an approval, I call `approve` at once with Camada's reference and summary,
  exactly as Camada gave them. My owner's own approval rule then asks them, and their answer
  decides. I never call it any other way, and I never decide for them. If they decline, I call
  `approve` again with their reason.
- Camada never asks for a password or a key in a conversation, and I never give one there.
- A file from Camada is a link for my owner to open.
- When Camada rings my webhook, I call `updates` and tell my owner what is new.

How each tool works is in the tool's own description, which is always current.

Version 2026-11-21.2.
