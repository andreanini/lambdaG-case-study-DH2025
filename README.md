# Examining an author’s individual grammar

This repository contains the abstract, a tutorial and the slides for the talk:

> Nini, A. ‘Examining an author’s individual grammar’. *Comparative Literature Goes Digital Workshop*, *Digital Humanities 2025*. Universidade Nova de Lisboa, Lisbon, Portugal. 14/07/2025.

The tutorial can be found here: <https://andreanini.github.io/lambdaG-case-study-DH2025/case_study.html>.

## Abstract

This demo talk will introduce the audience to a novel algorithm for stylometry called *LambdaG* (Nini et al. 2025). Although this method is designed as an authorship verification algorithm, this talk will demonstrate how it can also be used to study the unique grammar of an author.

Traditional stylometry techniques tend to be disconnected from linguistic theory. For example, although it is well demonstrated that the frequency of function words is a good discriminator of authors, it is still unclear why this is the case. Theoretical advancements to explain this phenomenon were made by Nini (2023), who proposed that these results can be accounted for by principles of Cognitive Linguistics (e.g. Langacker 1987). More specifically, what is crucial to the emergence of *linguistic individuality* is the concept of *entrenchment* (Bybee 2010; Schmid 2015; Divjak 2019).

The *LambdaG* method is fundamentally based on this idea by modelling entrenchment mathematically using grammar models. A *grammar model* is defined as a language model fitted on a text representation only containing functional items (e.g. *the* NOUN VERB *on the* NOUN). The method therefore exploits the notion of a *language model*, a probability distribution over stretches of language, which is a realistic mathematical model for procedural memory, the memory used for grammar processing (Ullman 2004).

The prediction made by Nini’s (2023) theory is that if a text was produced by a certain author, then the grammatical constructions in this text are more entrenched for this author than for random individuals in the reference population. *LambdaG* works by calculating the ratio between these two entrenchments for the questioned text. Experiments carried out on twelve different corpora validate this prediction and demonstrate that *LambdaG* is superior to many other verification methods, including methods based on Large Language Models or using neural networks.

Another advantage of *LambdaG* compared to other methods is that the *LambdaG* score is fully interpretable by an analyst, thus enabling them to identify which constructions characterise the unique language of an author. This can be done by producing text heatmaps that flag those sequences that are the most useful in identifying the author. For this reason, *LambdaG* can also be used very effectively to study the language of an author and to identify their unique linguistic identity.

The case study adopted for this talk is the analysis of Charles Dickens’ language. Using a corpus of 75 novels (3 novels for 25 authors) from Project Gutenberg (Schöch 2017), I will show how even a random sample of 1,000 words from Dicken’s *Bleak House* contains several constructions that seem to be idiosyncratic to Dickens, despite being seemingly unremarkable (e.g. *I could not* VP *without seeing it*; *it would have been* (*so much*/*far better*) *for me never to have* VERB-*past*).

The procedure to carry out this analysis will be shown step by step in R using the `idiolect` package (Nini 2024).

### References

Bybee, Joan. 2010. *Language, Usage and Cognition*. Cambridge, UK: Cambridge University Press.

Divjak, Dagmar. 2019. *Frequency in Language: Memory, Attention and Learning*. Cambridge, UK: Cambridge University Press. (20 October, 2019).

Langacker, Ronald W. 1987. *Foundations of Cognitive Grammar*. Vol. 1. Stanford, CA: Stanford University Press.

Nini, Andrea. 2023. *A Theory of Linguistic Individuality for Authorship Analysis* (Elements in Forensic Linguistics). Cambridge, UK: Cambridge University Press.

Nini, Andrea. 2024. Idiolect: An R package for forensic authorship analysis. <https://andreanini.github.io/idiolect/>.

Nini, Andrea, Oren Halvani, Lukas Graner, Valerio Gherardi & Shunichi Ishihara. 2025. Grammar as a behavioral biometric: Using cognitively motivated grammar models for authorship verification. arXiv. <https://doi.org/10.48550/arXiv.2403.08462>.

Schmid, Hans-Jörg. 2015. A blueprint of the Entrenchment-and-Conventionalization Model. *Yearbook of the German Cognitive Linguistics Association* 3(1). 3–25. <https://doi.org/10.1515/gcla-2015-0002>.

Schöch, Christof. 2017. refcor. <https://github.com/cophi-wue/refcor>.

Ullman, Michael T. 2004. Contributions of memory circuits to language: the declarative/procedural model. *Cognition* 92(1–2). 231–270. <https://doi.org/10.1016/j.cognition.2003.10.008>.
