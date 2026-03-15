---
layout: post
title:  "Book chapter on `Uncertainty-Aware DevOps for Cyber-Physical Systems and Runtime Verification`"
date:   2026-03-15 09:00:00 +0200
categories: update
author: Volker Stolz <vsto@hvl.no>
---

<div style="float:right; max-width:35%; padding-left:5px;">
<figure><a href="https://link.springer.com/book/10.1007/978-981-95-1786-2"><img src="https://media.springernature.com/full/springer-static/cover-hires/book/978-981-95-1786-2?as=webp" alt="book cover" />
<figcaption>Cover "Roadmap for DevOps in Cyber-Physical System — Challenges and Future Directions"</figcaption></a>
</figure>
</div>

Last year my colleague Violet and I had the chance to contribute to a chapter for the [book "Roadmap for DevOps in Cyber-physical systems"](https://link.springer.com/book/10.1007/978-981-95-1786-2#toc) (available from Springer) edited by Sebastiano Panichella, Paolo Arcaini, Myra B Cohen and Aitor Arrieta. This gave us the chance to finally look into the topic of Runtime Verification (RV) again, a topic that had brought me many good results and I felt I had been neglecting a bit. Sebastiano also summarised the book a bit on <strike>the other hell-site</strike> [LinkedIn](https://www.linkedin.com/feed/update/urn:li:activity:7426520284876173312/).

So together with a handful of usual suspects (Shaukat Ali, Domenico Bianculli, Antonio Cicchetti, Robbert Jongeling & Catia Trubiani), we brain-stormed a bit on what is and what could be in the field of DevOps. The RV-bit was mostly by us two and Domenico, and we identified some potential for RV in CI/CD-pipelines and how you'd go about it. In fact, I am still supervising Jakob Overrein, a Master-student at UiO, who's working on a thesis where be look at how DevOps and (e)BPF play along. We're in particular looking for repositories with pipeline-automations that either use BPF in the pipeline or deploy it.


<div style="clear: both;" />

Back to our book chapter on "Uncertainty-Aware DevOps for Cyber-Physical Systems and Runtime Verification" ([publisher's page](https://link.springer.com/chapter/10.1007/978-981-95-1786-2_5)) — here's the abstract:

> This chapter raises the attention on possible sources of uncertainties (e.g., workload of requests, software and/or hardware availabilities) that may arise at both development and operational stages (DevOps) in cyber-physical systems (CPS). Given that such uncertainties are unavoidable, a possible solution is to devise an uncertainty-aware methodology to model, analyze, and test these systems, thus anticipating glitches, if any. This way, we aim to monitor and verify the stated requirements at runtime, with the goal of guaranteeing that systems behave as expected. Our main contribution is to shed the light on the most relevant uncertainties (and to foresee their smooth handling) when applying the DevOps paradigm for CPS.

There's still plenty of work to do there, and RV seems like a good match to deal with uncertainties at runtime! Please do contact us or really any of the authors if you'd like to receive a copy of one of the chapters if your shop doesn't have a Springer-subscription!

This is also a reminder that <em>things take time</em>: we met for the seminar end of 2023, worked on the book through 2024/25, and it was published in early 2026...

It was such a pleasure to be "trapped" in Shonan with this excellent crowd, and we hope to do more work with people like Shaukat and Paolo where our interests overlap in the future :-) So enjoy this shot of Mt. Fuji and of the Norwegian participants to [Shonan seminar #204 "DevOps for Cyber-physical Systems"](https://shonan.nii.ac.jp/seminars/204/) as well! 

<center style="">
<figure style="max-width:45%; display: inline-block; vertical-align:top;">
<img src="https://cloud.elang.de/apps/files_sharing/publicpreview/pgCGNSFTns2xEBZ?file=/&fileId=331164&x=1643&y=1180&a=true&etag=8978dd08a7802b27dd3ad52571b06b69" alt="Fuji-san" />
<figcaption>Fuji-san</figcaption>
</figure>
<figure style="max-width:45%; display: inline-block; vertical-align:top;">
<img src="https://cloud.elang.de/apps/files_sharing/publicpreview/5RBkxjPHwHCEfWQ?file=/&fileId=1003899&x=1643&y=1180&a=true&etag=24a77fac4f6312a9f054eafa50cfe588" alt="Shaukat Ali (Simula), Violet Ka I Pun (HVL), Volker Stolz (HVL)">
<figcaption>Shaukat Ali (Simula), Violet Ka I Pun (HVL), Volker Stolz (HVL)</figcaption>
</figure>
</center>
