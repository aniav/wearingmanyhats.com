---
layout: post
title: "transaction.atomic good practices"
description: ""
date: 2020-10-13
permalink: /transaction-atomic-good-practices-d5e7187e05c9/
---
<!--more-->

When using transaction.atomic() we should remember that it can commit or rollback just the db related calls inside the atomic() block. It's not able to rewind a HTTP call, a call to redis or putting a payload on any queueing system. This means in case of a rollback we'd emit an event or call an external API to inform it about an object which effectively was not saved to the database.

In the project I’m working on now a real life scenario would e.g. end up sending an e-mail or an SMS to a person when their order was not created and customer support would need to deal with this.

A good practice is tho have the atomic() block the minimal set of db calls which have to be run together. Everything else should ideally be moved out.


📖 [Celery and transaction.atomic Stack Overflow thread](https://stackoverflow.com/a/40050417/808990)

📖 [Django docs on transaction.atomic](https://docs.djangoproject.com/en/dev/topics/db/transactions/#django.db.transaction.atomic)

📖 [Database transactions — How do they work?](https://stackoverflow.com/questions/3466632/database-transactions-how-do-they-work)