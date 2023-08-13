---
title: "Prompt-Tuning"
date: 2020-09-15T11:30:03+00:00
# weight: 1
# aliases: ["/first"]
tags: ["Prompt-Tuning", "Parameter-Efficient-Fine-Tuning"]
author: "Me"
# author: ["Me", "You"] # multiple authors
showToc: true
TocOpen: false
draft: false
hidemeta: false
comments: false
description: "In this blog I'm sharing my learning about Prompt-Tuning"
canonicalURL: "https://canonical.url/to/page"
disableHLJS: true # to disable highlightjs
disableShare: false
disableHLJS: false
hideSummary: false
searchHidden: true
ShowReadingTime: true
ShowBreadCrumbs: true
ShowPostNavLinks: true
ShowWordCount: true
ShowRssButtonInSectionTermList: true
UseHugoToc: true
cover:
    image: "<image path/url>" # image path/url
    alt: "<alt text>" # alt text
    caption: "<text>" # display caption under cover
    relative: false # when using page bundles set this to true
    hidden: true # only hide on current single page
editPost:
    URL: "https://github.com/<path_to_repo>/content"
    Text: "Suggest Changes" # edit text
    appendFilePath: true # to append file path to Edit link
---

### Introduction

In Prompt-Tuning, we change the input token according to the task at hand, instead of learn or finetune the parameters of the whole model.

There are two different kinds of prompt tuning techniques:
* Hard Prompt-Tuning
* Soft Prompt-Tuning

### Hard Prompt-Tuning
Different Prompt-Engineering tricks will be used to model understand and perform well on the task at hand.

Examples:
* Zero-shot Prompting
* One-shot Prompting
* Few-shot Prompting

### Soft Prompt-Tuning
In Soft Prompt-Tuning the input tokens will be learned by backpropagation instead of designing by hand, ie, we let the model learn the input tokens. In this we concatenate the learned tokens along with our input tokens.

Storage Efficiency is provided by Prompt-Tuning, because we are not tuning the whole model parameters. So we can use the same base model and learn different prompts for each tasks.

For models less than 12B parameters, Prompt-Tuning has effects similar to full model finetuning.

### References
[1] ["<ins>SEBASTIAN RASCHKA, PHD</ins>"](https://magazine.sebastianraschka.com/p/understanding-parameter-efficient)
