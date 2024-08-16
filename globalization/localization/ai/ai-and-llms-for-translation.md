---
title: Use AI and large language models for translation
description: Discover how large language models (LLMs) are revolutionizing localization, offering near-human quality and versatility in multilingual applications.
author: jowilco
ms.author: jowilco
ms.topic: conceptual #Required; leave this attribute/value as-is.
ms.date: 08/15/2024
ms.custom:
  - ai-gen-docs-bap
  - ai-gen-desc
  - ai-seo-date:08/15/2024
---

# Using artificial intelligence and large language models for translation

With recent advances in large language models (LLMs), there's much discussion around whether to use AI instead of existing machine translation (MT) systems or even as a replacement for human translation (HT). The latest LLMs are performing well, getting close to HT-level quality, especially for certain language pairs. However, LLM-based solutions have some drawbacks, which include:

- LLMs might not perform as well as existing technologies, such as neural machine translation (NMT), especially for fields with specialized terminology such as healthcare.
- LLMs take longer and are more expensive to train than NMT
- LLMs are slower and require more processing power than NMT

LLMs are evolving rapidly, costs are decreasing, and speed is increasing year over year, so many of the current concerns might be less relevant in the future.

## Large language models in software and globalization

Generative AI is a type of artificial intelligence focused on the ability of computers to use models to create content like text, synthetic data, and images. Generative AI applications are built on top of generative AI models such as large language models (LLMs).

LLMs are deep learning models that consume and train on massive datasets, allowing them to excel in language processing tasks such as translation. After these models have completed their learning processes, they generate statistically probable outputs when prompted. The models create new combinations of text that mimic natural language based on their training data.

The development of LLMs has been a gradual process. The first LLMs were relatively small and could only perform simple language tasks. However, with the advances in deep neural networks, larger and more powerful LLMs were created. The 2020 release of the Generative Pre-trained Transformer 3 (GPT-3) model marked a significant milestone in the development of LLMs. GPT-3 demonstrated the ability to generate coherent and convincing text that was difficult to distinguish from text written by humans.

GPT-3, and subsequent models, have been trained on datasets in multiple languages; therefore, these models are able to generate output in multiple languages. However, the quality of the output in each language is related to the amount of training data in that language. Languages where the LLMs were trained with a large set of data are considered *high-resource* languages. Languages that were trained with smaller sets of data are considered *low-resource* languages.

AI and LLMs have the potential to be transformative technologies for globalization. While LLMs weren’t trained specifically for translation, their broad applicability to natural language tasks means that they perform well for translation, especially for high-resource languages. In addition, LLM features in a product often perform well for languages other than the original product language.

## Artificial intelligence and translation technology

### Advances in machine translation

Machine translation (MT) systems are applications or online services that use technology to translate text between any of their supported languages. Although the concepts behind machine translation technology and the interfaces to use it are relatively simple, the science behind it is complex and it brings together several leading-edge technologies. There has been an evolution in approaches to machine translation, including:

- Rules based machine translation: machine translation based on dictionaries and grammar rules of each language
- Statistical machine translation: machine translation based on statistical analysis of bilingual text corpora
- Neural machine translation (NMT): NMT also uses statistical analysis to predict the likelihood of word sequences. It relies on neural networks to model entire sentences.

These technologies have transformed the translation and localization industries. They’ve delivered increased productivity, reduced costs, improved consistency and scalability, and the ability to easily handle domain-specific terminology.

Nontheless, advances in large language models (LLMs) are enabling new paradigms for natural language processing tasks, which include translation. LLMs have the potential to outperform NMT, while enabling [natural language processing features](localizing-ai-based-features.md) in multilingual applications.

### Using large language models in your translation workflow

Adopting AI for translation is a forward-thinking approach that aligns with the latest advancements in technology. It’s essential to transition to this new process thoughtfully and incrementally, ensuring that it meets established benchmarks for each language before full implementation.

When evaluating the case for shifting to AI-based translation, it’s crucial to consider various factors such as:

- risk management
- ensuring high-quality outputs
- the total cost of ownership
- the system’s performance

The transition to AI should be a step-by-step process, tailored to the specifics of each product, content type, market, language, and customer expectations. This approach allows for a balanced and justified move towards AI, especially in cases where the return on investment might be minimal.

In terms of risk, AI-based translation carries a new set of challenges that require thorough human evaluation. Ensuring [responsible AI](./ai-and-localization.md#what-is-responsible-ai) usage is paramount, particularly for sensitive applications, to maintain the integrity of the brand and manage potential reputational risks. Special attention should be paid to new or updated terminology, and frequent spot-check validation of the LLM updates, as newer versions of the models might introduce degradation for some languages.

Quality control is variable across different languages. While AI-based translation has exceeded or matched the quality of traditional methods in some languages, it still poses significant challenges in others. The focus of the quality reviews should include two factors: linguistic quality, and adequacy. Ensure that the text is appropriately written following the required linguistic quality required by your products and is an adequate translation for the source. The latter is specially important since, as opposed to MT, LLMs can introduce *fabrications* or *hallucinations*. Fabrications are words or phrases that aren't present in the source text but are generated by the model. The fabricated text might be factually correct, but it can also be incorrect or misleading, even when the text seems plausible.

Cost-wise, some of the latest AI models are slightly cost-effective than their predecessors. However, the total cost of ownership, which includes both the operational and personnel costs, must be taken into account.

### Neural machine translation vs large language models

Many of the current state of the art-translation applications, such as [Microsoft Translator](https://www.microsoft.com/translator/business/), are based on neural machine translation (NMT). NMT is an improvement on previous statistical machine translation (SMT)-based approaches as it uses far more *dimensions* to represent the tokens (such as words, morphemes, and punctuation) of the source and target text.

Unlike NMT, large language models (LLMs) weren't designed for translation. However, as LLMs are designed to excel at language processing tasks, they often perform well at translation, especially between high-resource language pairs.

There are similarities between NMT and LLM:

- Both are pretrained using bilingual (or multi-lingual) corpora
- Both can be trained, or [fine-tuned](/ai/playbook/technology-guidance/generative-ai/working-with-llms/fine-tuning), to perform better for specific tasks

However, there are also differences that means that NMT or LLMs might be the most appropriate technology, depending on the task:

- It’s easier and cheaper to fine-tune NMT for specific domains, such as healthcare.
- LLMs, in general, produce more natural-sounding text, while NMT produces more accurate text.
- NMT typically processes segment by segment, while LLMs can work on entire documents at once. So, LLMs perform better with explicit context.
- It can be easier to integrate existing glossaries and term bases with NMT than LLMs.
- NMT performs faster than LLMs; however, newer LLMs perform better than previous LLMs. Speed might be a significant concern for processing large volumes of text.
- Processing translations using LLMs is more expensive than NMT. This is especially true for low-resource languages.
- NMT can be optimized for language variants. LLMs might have trouble differentiating between and producing text for language variants such as Portuguese for Portugal and Brazilian Portuguese.
- NMT is optimized specifically for translation while LLMs can be used for various language processing tasks. For example, an LLM could be used to create a business email in Japanese.

## Using LLMs for localization tasks other than translation

Due to their wide applicability for language processing tasks, consider using LLMs for other tasks in your localization workflow. For example,

- LLMs might be suitable for linguistic review of human-translated or machine-translated text.
- LLMs can be used to generate test data in multiple languages.
- LLMs might produce better output than other machine translation methods for responses to technical support requests if your team can't support a language natively.

As you consider using LLMs for localization tasks, remember that LLMs need to be used [responsibly](./ai-and-localization.md#what-is-responsible-ai). Ensure that you're validating the output of the LLMs and that you're using diverse and representative datasets to train the LLMs.
