---
layout: post
title: Unsupervised representation learning of whole slide images.
date: 2024-01-15
description: Blog post to present both our new pre-print as well as its companion package.
tags: histopathology SSL representation biomarker
categories: sample-posts
giscus_comments: true
related_posts: false
toc:
  sidebar: left
---

**[Super simplistic figure showing WSI -> gigassl -> single embedding]**

[Announcing the release of all ou GigaSSL models, and associated embeddings for all TCGA and CTAC !]

[In a serie of two papers, [link1] and [link2], we present a novel unsupervised slide-level representation learning framework for computational pathology.]

[introduction of the alternative = frozen embeddings + MIL]
[Here, replace MIL with a pretrained model - reaches supervised alternative performances.]

[Using this framework, we trained models on all the FFPE slides of the TCGA.]
[The slide embeddings of these pre-trained models present:]
[* Discriminative power superior or comparable to MIL embeddings trained using weak supervision on 5 key benchmark tasks.]
[* Great generalization power outside of TCGA, without any re-training or fine-tuning.]
[* Can be computed in 5 to 10 seconds per slide, using a single GPU and a simple command line.]
[* Already proved useful - ranked 4th at the Visiomel challenge (3rd price of 5k$, 2nd place regarding the AUC metric)]

[They therefore offer:]
[* A super simple solution to iterate experiments quickly with your dataset of WSIs.]
[ In computational pathology more than in any other field, experimenting is hindered by the very wide size of WSIs, requiring heavy pipelines to process.]
[ With the GigaSSL representations, the early experimentation process of you ML project using WSIs can be done on a laptop, with linear models.]
[ Example: *is this variable predictable ?*, *Should I stratify my dataset to predict this variable (for instance, should I train a separate model for biopsies and surgical resection ?)*
*Is there any spurrious correlation w.r.t the output variable* ?]
[* A strong easy benchmark model to test against.]
[ When developing a new model, logistic regression on top of GigaSSL representations offer a computationally free SoTA or near SoTA algorithm to compare to and iterate in the developpment.]
[* A good entry point to use pathology data in addition to other modalities.]

## HOW TO ?

Accompanying each paper, you can find code to:

- [Train your own Giga-SSL model](https:github.com/trislaz/gigassl)
- [Encode WSIs in 5-10 secs with pre-trained models](https:gitub.com/trislaz/Democratizing_WSI)

I trained GigaSSL models using available open-source tile encoder models, that include:

- A ResNet18 trained with MoCo
- CTransPath -link to pub + gitub-
- Phikon -link to pub + huggingface-

[All these models are made available.]
[If you are developing a tile-encoder model and want to collaborate, contact me and I'll be happy to train or help you train a GigaSSL model on top of them and make it available here.]
