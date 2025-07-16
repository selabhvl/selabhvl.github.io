---
layout: post
title:  "Theses on connecting RTLola via FMUs and a bit of a null-result on using LLMs for code generation"
date:   2025-07-16 08:56:14 +0100
categories: science, llms, runtime verification
author: Volker Stolz <vsto@hvl.no>
fediverse: "@fm_volker@mastodon.social"
---

Two of my MSc students at UIO finished this summer, [Selleban Mohamud Farah on "FMUs for runtime monitoring in RTLola"](https://www.mn.uio.no/ifi/english/research/groups/psy/completedmasters/2025/farah/),
and [Jonas Lien Sampaio da Silva on "Towards Automated Language Server Synthesis"](https://www.mn.uio.no/ifi/english/research/groups/psy/completedmasters/2025/da-silva/).

For both there's a little web-page with the abstract, slides and other material linked above.
It takes a while for the official thesis PDF to percolate through the system and get published on [DUO](https://duo.uio.no),
which is in a bit of a flux-state right now due to the migration to a new national archive.
Contact them directly for their theses or check their repos!

Both did some hacking along the way and probably learned a lot (Selleban learned himself some Rust and Jonas wrote some serious Prolog-bits) :-)
As usual, with hindsight one could've made different decision here and there along the way and possible have improved results a bit,
but overall I'm quite happy since both worked very independently and a lot is clearer to me now and can be put to use by other
MSc- or PhD students.

While Selleban's work was in the style of "some assembly required", combining existing technologies and possibly giving us better ways of using specifications in monitoring systems **concretely** in the future, Jonas used an LLM to generate a (working) boilerplate for the Language Server Protocol based on DSL-fragments. What we'll have to look closer at in the future is in how far we can expect the LLM-*du jour* to get semantic relations (like `def-use`) right.
