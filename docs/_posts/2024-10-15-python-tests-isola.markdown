---
layout: post
title:  "Automated Clone Elimination in Python Tests (ISoLA'24)"
date:   2024-10-15 10:56:14 +0200
categories: update
author: Volker Stolz <vsto@hvl.no>
fediverse: "@fm_volker@mastodon.social"
---

My co-author Violet and I are almost on the way to the [ISoLA-conference](https://2024-isola.isola-conference.org) where I will present our work with our excellent MSc student Sebastian Kingston from UiO on "Automated Clone Elimination in Python Tests" in the Automated Software Re-engineering-track!

Our contribution is based on [Sigrid Eldh's observation at an earlier ISoLA](https://doi.org/10.1007/978-3-031-19756-7_17) on what issues industry actually faces in testing. You can find [Sebastian's thesis at UiO](https://www.duo.uio.no/handle/10852/112541).

### Abstract:

Code clones are a well-known software quality metric with existing tools for detection and (semi-) automated elimination for common programming languages. While they are usually eliminated by extracting duplicate code into shared methods/functions, we are here looking in particular at Python code for test cases, where clones stem from repeated test cases with primarily different arguments and expected results. In this scenario, the ideal solution is not introducing shared code, but rather using parametrized tests from the unit testing framework. We combine an existing clone detector ([NiCad](https://www.txl.ca/txl-nicaddownload.html)) with our own code transformation that eliminates code clones in Python test cases using the pytest framework. We show the usefulness of our approach by surveying open source Python projects that can benefit from our refactoring and evaluate the performance and correctness of our transformation by comparing unit-test results before and after.

Preprint: [PDF](https://foldr.org/~vs/slides/isola24-article.pdf)
Slides: forthcoming
