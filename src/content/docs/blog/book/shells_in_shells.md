---
title: Shells in shells
---

## Working in multiple directories

While it's common to work in one directory, it can be handy to work in multiple places at the same time. For this, Nu offers the concept of "shells". As the name implies, they're a way of running multiple shells in one, allowing you to quickly jump between working directories and more.

To get started, let's enter a directory:

```nu
/home/jonathan/Source/nushell(main)> enter ../book
/home/jonathan/Source/book(main)> ls
────┬────────────────────┬──────┬────────┬─────────────
 #  │ name               │ type │ size   │ modified
────┼────────────────────┼──────┼────────┼─────────────
  0 │ 404.html           │ File │  429 B │ 2 hours ago
  1 │ CONTRIBUTING    │ File │  955 B │ 2 hours ago
  2 │ Gemfile            │ File │ 1.1 KB │ 2 hours ago
  3 │ Gemfile.lock       │ File │ 6.9 KB │ 2 hours ago
```

Entering is similar to changing directories (as we saw with the [`cd`](/commands/docs/cd) command). This allows you to jump into a directory to work in it. Instead of changing the directory, we now are in two directories. To see this more clearly, we can use the [`shells`](/commands/docs/shells) command to list the current directories we have active:

```nu
/home/jonathan/Source/book(main)> enter ../music
/home/jonathan/Source/music(main)> shells
───┬────────┬───────────────────────────────
 # │ active │             path
───┼────────┼───────────────────────────────
 0 │ false  │ /home/jonathan/Source/nushell
 1 │ false  │ /home/jonathan/Source/book
 2 │ true   │ /home/jonathan/Source/music
───┴────────┴───────────────────────────────
```

The [`shells`](/commands/docs/shells) command shows us there are three shells: our original "nushell" source directory, "book" directory and "music" directory which is currently active.

We can jump between these shells with the [`n`](/commands/docs/n), [`p`](/commands/docs/p) and [`g`](/commands/docs/g) shortcuts, short for "next", "previous" and "goto":

```nu
/home/jonathan/Source/music(main)> p
/home/jonathan/Source/book(main)> n
/home/jonathan/Source/music(main)> g 0
/home/jonathan/Source/nushell(main)>
```

We can see the directory changing, but we're always able to get back to a previous directory we were working on. This allows us to work in multiple directories in the same session.

## Exiting the shell

You can leave a shell you have [`enter`](/commands/docs/enter)ed using the `dexit` command.

You can always quit Nu, even if multiple shells are active, using `exit`.