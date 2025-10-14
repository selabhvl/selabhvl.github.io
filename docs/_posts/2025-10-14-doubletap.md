---
layout: post
title:  "Double-tap: our papers at SBMF & DataMod"
date:   2025-10-14 20:56:14 +0100
categories: science
author: Volker Stolz <vsto@hvl.no>
fediverse: "@fm_volker@mastodon.social"
---

Q: What's better than having to submit a camera-ready copy to the publisher? \
A: Having to submit **two** on the same day!

Violet, Volker and Charaf had their submission at [SBMF'25](http://sbmf2025.ufrpe.br) accepted on "Resource Contracts for Active Objects" ([preprint](https://foldr.org/selabhvl/2025/sbmf25-preprint.pdf)).
Again there's a Maude-artefact in case you want to play with it: [https://github.com/selabhvl/maude-active-objects](https://github.com/selabhvl/maude-active-objects).

Our Phd student Ivan had a submission on "Ruleless Digital Twins" together with Volker at [DataMod](https://datamod-symposium.github.io/DataMod-2025/) accepted (co-located with SEFM). Also there we have
a [pre-preprint](https://foldr.org/selabhvl/2025/2025-datamod-prepreprint.pdf) and an [artefact](https://github.com/ivanspajic/ruleless-digital-twins).
We also had a fun time finding and submitting bugfixes for Open Modelica and the [C# bindings for FMI](https://github.com/selabhvl/vsto-Femyou).

---

###  "Resource Contracts for Active Objects", Charaf Eddine Dridi, Violet Ka I Pun, Volker Stolz

Workflows coordinate tasks across departments or organistions, where correct execution depends not only on control dependencies
but also on the availability of shared resources. This paper presents **ReAct**, a resource-aware active object language for workflow modelling. In
ReAct, method declarations serve as contracts: they specify alternative
resource profiles in their signatures, giving methods multiple execution
options when resources are limited. Methods can be invoked only once
their dependency conditions are satisfied; at activation, a feasible resource profile is then selected and allocated. We encode the language in
Maude and show how workflows can be executed, simulated, and verified
against their declared dependencies and resource requirements.

### "Ruleless Digital Twins", Ivan Spajić, Volker Stolz

We introduce a transparent digital twin (DT) decision-making
approach without the use of explicit decision rules or rule-based models. Our approach utilizes ontological inference and simulation models
to explore possible decisions before applying them to the twinning target. As proof of concept, we provide an implementation of the proposed
framework purely based on widely-known technologies and standards,
and subsequently demonstrate the feasibility of our approach. We discuss benefits and drawbacks, and recognize that a ruleless approach to
DT decision making ultimately rests on an effective method of choosing from a multitude of possibilities. Lastly, we consider potential future
work and exploration in the context of more effective automation and
simulation model usage.
