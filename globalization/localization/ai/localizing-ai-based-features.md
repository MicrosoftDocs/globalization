---
title: Localize artificial intelligence-based features
description: Optimize AI features for global markets by customizing LLM outputs to meet diverse language and cultural needs, ensuring alignment with business goals and user expectations.
author: jowilco
ms.author: jowilco
ms.topic: conceptual #Required; leave this attribute/value as-is.
ms.date: 08/15/2024
ms.custom:
  - ai-gen-docs-bap
  - ai-gen-desc
  - ai-seo-date:08/15/2024
---

# Localizing artificial intelligence-based products and features

AI-based products and features have become more prevalent since the 2020 release of the Generative Pre-trained Transformer 3 (GPT-3) large language model (LLM). These features are usually designed to support the source-language market. While other language support might be easy to enable, you shouldn't assume that features will work without more extended customization.

It's essential to ensure that the LLM's outputs align with business goals and user expectations. Consider an LLM generating marketing emails. Without evaluation, these emails might come across as too formal, too casual, or too generic, depending on the target language. By assessing a sample of outputs for each target language, you can optimize their impact and relevance, making sure they effectively meet the business's objectives and resonate with the target audience.

## Generating output in non-source languages

There are two general approaches when creating output from LLMs in languages other than the original language:

1. Translate the prompt into the target language and have the LLM respond in that language.
1. Use the source language prompt, but ask the LLM to return the output in the target language.

Either approach might be most appropriate for your prompt, use case, and source/target language pair. Testing the output then becomes critical to ensuring the best chance of supporting your customers in their language.

## LLM prompt engineering and testing the output

Large language models (LLMs) can learn new tasks on the fly, without requiring any explicit training or parameter updates. This mode of using LLMs is called in-context learning. It relies on providing the model with a suitable input prompt that contains instructions and/or examples of the desired task. The input prompt serves as a form of conditioning that guides the model's output.

The process of designing and tuning the natural language prompts for specific tasks, with the goal of improving the performance of LLMs is called *prompt engineering*. Effective prompt engineering can significantly improve the performance of LLMs on specific tasks. It's done by providing instructions and contextual information that help guide the model's output. Researchers can steer the LLM's attention toward the most relevant information for a given task by carefully designing prompts, leading to more accurate and reliable outputs.

If you intend to start with a source language prompt, then translate it for each target language, you shouldn't assume that just translating the prompt will be sufficient. Prompt translation is akin to translating marketing materials, in other words, [transcreation](../transcreation.md). While the translated prompt might be a good starting point, you'll need to repeat the prompt engineering process for each target language.

## Considerations for effective LLM prompts

### Region availability

You should ensure that the AI technology that you're planning to use is available in all the regions and for all the locales that you would like to support. Some AI technologies are subject to export restrictions and if these technologies are a critical component of your implementation then you might be limited to specific regions.

### Handling regional formats

Even when the same language is used for two or more locales (for example, English for US, UK, and Australia), if your LLM output contains data that need to be formatted according to [regional formats](../../locale/regional-settings.md), you might need to specify the locale of the output in the prompt. Evaluate the prompt response using the names of the country/region and language combination and [IETF BCP 47 locales](../../locale/standard-locale-names.md) to see which produces the most appropriate output for your use case.

### Customizing for different cultural contexts

The level of formality for a business email for a recipient in the US will be different than a business email for a recipient in Japan, or even the UK. Consider the audience when prompt engineering for multiple languages and locales.

### Content moderation

Your source language prompt might include *content moderation*, for example, specifying terms or words that shouldn't be used in the response. Content moderation might also attempt to use the prompt to make responses suitable for a specific age group or to meet national content requirements. You might need to adjust the prompt so that content moderation is still appropriate for the target language or locale.

### Cross-border data flow and AI laws

Cross-border data flow is about the transfer of data across national borders, which is pivotal for global software development projects. Compliance with regional data protection laws and ensuring adequate computing resources are critical aspects that require meticulous planning and execution.

The computing resources that are hosting your LLMs might be in a different geography than other resources that you're using. Ensure that you're still compliant with regulations like the General Data Protection Regulation (GDPR) in Europe that can restrict data movement, aiming to protect privacy and national security.

The EU Artificial Intelligence Act includes stringent requirements for high-risk AI systems, adds another layer of complexity by imposing strict standards on data usage, transparency, and accountability. These regulations can pose challenges for AI development, as they require careful navigation to balance innovation with privacy and security concerns.
