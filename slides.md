class: middle, center, title

# Skillful Notes

## Productive writing with _just_&nbsp;enough&nbsp;complixity

### Ryan Parsley

#### 2024-08-26

???

Let's talk about where your personal notes stop and shared documentation starts.
I've been thinking a bit on how to smoothly transition from one class of writing
to the other and am looking forward to sharing some tips and tricks.

---

class: middle, center, title

# This is _not_ a presentation about markdown

(Thanks for the slide Craig)

???

Markdown is great and I believe I use it to great effect in some of the following
examples, but this is not a presentation _about_ markdown. This is a
presentation about thinking and communicating.

It's about selecting the right tool for the job and knowing when adhering to the
tech stack is not a prerequisite.

---

# A brief history of Markdown

> Markdown’s syntax is intended for one purpose: to be used as a format for
> writing for the web.
>
> &mdash;John Gruber

???
John Gruber made an ergonomic dialect to speed up the writing process for his
static site blog.

It's not his fault developers got a little "too" into the idea.

---

# Does `X` _support_ markdown?

> A Markdown-formatted document should be publishable as-is, as plain text,
> without looking like it’s been marked up with tags or formatting instructions.
>
> &mdash;John Gruber

???

Yes, that's the beauty of markdown. Even in the complete absence of "support"
you can still read it just fine. I can write markdown on a piece of paper with a
pen and you can pick up what I'm putting down.

Lack of rich text support in early iPhone created a hole that markdown filled.

Once it was a popular enough defacto standard, devs made support for it better
and better.

Depending on how you look at it we're talking graceful degradation or
progressive enhancement here.

As you venture into advanced markdown territory, focus on that objective. That's
a pretty good north star.

---

background-image: url(./assets/standards.png)
background-size: auto 400px

# Standards

???

Markdown gets a bad rap with respect to compatibility because of 2 issues.

1. Historically, predicting support was tricky
2. People's expectations are poorly calibrated

Gruber had by design a very spartan list of tags. He was a writer and designed
and API of sorts optimized for writing.

# Commonmark

This is a reasonable place to start if you want to consider a superset of what
Gruber set out to achieve.

# GFM

Strict superset of common mark now, but really, I'd just stick to Common mark
and extend it via your parser's ecosystem

# ADO

ADO does _not_ support common mark. It claims to support GFM, but seems like it
more accurately reserves the right to support a subset of GFM while also doing
it's own thing. That's fine. Stick to the gruber stuff and you'll have a good
time.

---

# Extensions, that's where they get you

???

Know that there are various standards and degrees of not following said
standards. I don't want to get into the weeds on parsers. Whatever language or
context you're working with markdown, check for commonmark support and you're
mostly good to go.

It's worth becoming familiar with the common denominator of various
parsers so you can be aware of what's likely to not work when you port your data
from one platform to another.

Every parsing option has a different means of extending commonmark. That is very
powerful, but also the point at which you are compromising on portability. This
compromise is sometimes reasonable and worth it. Just be aware of it.

---

# Markdown TLDR

- Most parsers don't mess up what gruber defined
- If you're picking a tool, confirm they support CommonMark
- you can extend CommonMark, through plugins based on the parser you select
- Compatibility is largely solved by 2024

---

class: middle, center, title

# This is _not_ a presentation about markdown

???

I said all that because I continue to use markdown as my writing standard of
choice. There are others. I've considered org mode an neorg but I like the
ubiquity of markdown and gruber's subset is what I use the vast majority of
writing. My whole career, I've been making websites, a big chunk of that was
customizing content management systems.

---

# Structure is good

As you apply structure to your notes... you'll be encouraged to structure your
thoughts.

## What is the true nature of this data?

It's not always obvious when you stop to think about it.

---

# What's the killer feature of Obsidian?

## First place

### The community

## Tied for second

### Ergonomics and Extensibility

???

Let's talk a little about tools.

This is also not a presentation about obsidian.

I'm not anti-obsidian.

I don't use it for work anymore but I still keep my personal notes on it.

The obsidian community has put out a ton of great content that's helped me focus
my own thoughts on note taking.

PKM, zettlekasten, second brain are all concepts that I learned through an
obsidian lense. But you don't _need_ obsidian for any of that.

# First

The Obsidian community is full of thoughtful content creators sharing tips and
tricks.

# Second

The features I love most about Obsidian were written by a member of the
community.

- dataview
- tracker (habit tracking)
- periodic notes (better than 1st party daily)
- templater (better than 1st party templates)

---

# In other words

> I would look for obsidian plugins that are along that path, and then work
> backwards into what they are using.
>
> &mdash;Craig

???

Craig pretends like he's not collaborating on this slide, but I know the reason
there's only one set of footprints.

---

# When Obsidian starts feeling wrong to me

````markdown
```dataview
TABLE author, published, file.inlinks AS "Mentions"
FROM #poems
```
````

???

Dataview is one of my favorite parts of Obsidian and also a bit of a smell with
respect to the litmus test of "Does publishing this read well unrendered?"

It's easy to reason about what that does, but it means nothing outside of
obsidian.

I am uneasy making the compromise that this extension demands.

---

class: middle, center, title

# What does "future proof" mean!?

???

I care about transferable skills. I switched from vim to neovim... when I used
obsidian for notes, I turned on vim mode. Learning vim motions helps me not
_just_ in vim.

I like about mermaid syntax, I can type it in ado, I can type it in vim, I can
render it in mdbook... it's not tightly coupled to any one environment or
context.

Dataview does not share that.

---

background-image: url(./assets/slidesInVim.png)
background-size: auto 400px
background-position: 50% 60%

# What's the killer feature of any decent editor/ IDE?

???

Powerpoint certainly doesn't share that :D

I hope among the top 5 are... ergonomics and extensibility!

Ok, so why would a dev _not_ want to trick out their editor instead of using
Obsidian?

---

# LSP

## Language Server Protocol

### Examples

- Markdown Oxide
- Marksman

### Features

- follow links
- count references
- complain about dead links

???

LSPs are what fuel your editor's syntax highlighting and code suggestions.

And they can turbo charge your markdown experience much the same way.

---

# Documentation as code

---

# But, ADO can't parse that

BYO parsing if you care to

---

class: middle, center, title

# But Ryan, I don't like editing tables in markdown

---

class: middle, center, title

# Yeah, me neither. Don't do that

???

If I'm editing a lot of data manually for some reason, I'm probably tucking that
in frontmatter.

The occasional trivial table is fine like half a dozen columns
or less and not many more rows. Think less excel alternative and more, neatly
arrange features and benefits. Just because you write text in markdown doesn't
mean you _need_ every aspect of your docs to be constrained to markdown syntax.

You can _just_ consume data from a CSV or whatever works for you.

When you make a website, you write html, but include images, audio, whatever you
need.

Markdown is just html without the stabby brackets.

---

background-image: url(./assets/csvNushell.png)
background-size: auto 130px

# Don't sleep on CSVs

???

They're easy to create and reason about. One can open them as a spreadsheet and
you can parse them into whatever asset makes sense to best tell their story.

---

# Recutils

> The data is stored as a sequence of records, each record containing an
> arbitrary number of named fields.
>
> &mdash;[Project Docs](https://www.gnu.org/software/recutils/)

???

There's a ton of tools out there you've never used.

---

# Gnuplot

```gnuplot

set terminal svg enhanced background rgb 'white';
set output 'assets/performance-summary.svg';
plot 'assets/performance-summary.txt' with lines
  title 'Match Performance Over Time';

```

???

Gnuplot has been actively developed since 1986.

It had a major release this year!

---

# Gnuplot (less trivial)

```gnuplot
set xdata time;
set ylabel 'Initial Bundle Size (Mb)';
set xlabel 'Date';
set timefmt '%Y-%m-%d';
set xrange ['2023-10-01':'2024-12-31'];
set yrange [0:4];
set terminal svg enhanced background rgb 'white';
set datafile separator ",";
set output '../.assets/performance-summary.svg';
warning(x) = .5;
error(x) = 1;
plot
    '../.assets/data.csv' using 1:2 with lines title 'Hello World',
    warning(x) title 'Default Warning Threshold' lt rgb 'orange',
    error(x) title 'Default Error Threshold' lt rgb 'red';
```

---

background-image: url(./assets/performance-summary.svg)
background-size: auto 400px
background-position: 50% 60%

# Gnuplot (output)

???

Gnuplot runs in a pipeline, meaning you can generate a CSV and render a chart
from that and embed it in your wiki. ADO Markdown doesn't _need_ to support
javascript or some bespoke plugin. It supports linking up images.

---

background-image: url(./assets/noPowerInTheVerseCanStopMe.gif)
background-size: auto 400px

# "Plain" text

---

background-image: url(./assets/folderOfAudits.png)
background-size: auto 400px
background-position: 50% 75%

# Bundle Audits from Notes

## Folder stucture

???

Nothing too fancy, every couple of months I'd periodically make notes on the
build.

---

# Bundle Audits from Notes

## A given note

```markdown
---
buildTag: 3.55.0
commit: 8b3280
bundleSize: 1.88
---

# 2023 Q4

Write some notes about what was going on at the time, maybe.
```

???

This is a common enough approach with obsidian and I had a plugin that would
enable a higher order note to render a chart based on the bundleSize
frontmatter.

This was powerful. It helped me understand and craft a narrative of progress
over time that was not supported by how we operate ADO.

Simple ideas like this can havea profound impact on how you see opportunities
and challenges.

---

# Bundle Audits from Notes

## Script to scrape frontmatter

```nu
['2019', '2020', '2021', '2022', '2023']
  | each {|| ls $in}
  | flatten
  | where $it.name != matchPerformanceQuarterly.md
  | each {
    |file| $"(open $file.name)"
    | find "bundleSize"
    | first
    | split column ":" key value
    | get value
  }
  | flatten
  | save $output -f
```

---

# Bundle Audits via pipeline

## Calculate bundle size

```nu
def calculateInitialBundleSize [] {
  open dist/stats.json
    | get assets
    | where {
        | asset | $asset.name in [
          'main.js',
          'polyfills.js',
          'my-styles.css',
          'styles.css',
          'foundationBase.css',
          'runtime.js',
          'scripts.js'
        ]
      }
    | get size
    | math sum
}
```

???

To me, this feels slick. You're using the angular cli to generate a source of
truth, but exposing the data via a focused lense.

---

# Bundle Audits via pipeline

## Gather context from git

```nu
def getLastCommitDetails [] {
  git log --pretty=%h»¦«%s»¦«%aN»¦«%aE»¦«%aD
  | lines
  | split column "»¦«" commit subject name email date
  | first 1
  | insert initialBundleSize (calculateInitialBundleSize)
}
```

???

But, even better... you can combine data in any way that helps you craft a
narrative. People say "the data can't lie".

A lot of times, it mumbles.

Help it articulate.

---

# Bundle Audits via pipeline

## Save it to a CSV

```nu
def main [] {
  open bundleLog.csv
  | append (getLastCommitDetails)
  | collect
  | save bundleLog.csv --force
}
```

---

class: middle, center, title

# This is _not_ a presentation about bundle audits

???

I hope seeing some of what I've been noodling with inspires you to solve your
own problems in delightful ways. If so please share me the weird and creative
code you write.

---

# References

## Tools I use

- [Zellij (multiplexor)](https://zellij.dev/)
- [Stow (helps manage dot files)](https://www.gnu.org/software/stow/manual/stow.html)
- [mise (polyglot version manager)](https://mise.jdx.dev/getting-started.html)
- [WezTerm (terminal emulator)](https://wezfurlong.org/wezterm/index.html)
- [Neovim (editor)](https://neovim.io/)
- [Remark (markdown powered slides)](https://github.com/remarkjs/remark)
- [Nushell (alternative shell)](https://www.nushell.sh/)

???

---

# See Also

- [GFM Docs](https://github.github.com/gfm/)

???
