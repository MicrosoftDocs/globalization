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

## Engineering LLM prompts and testing the output

Large language models (LLMs) can learn new tasks on the fly, without requiring any explicit training or parameter updates. This mode of using LLMs is called in-context learning. It relies on providing the model with a suitable input prompt that contains instructions and/or examples of the desired task. The input prompt serves as a form of conditioning that guides the model's output.

The process of designing and tuning the natural language prompts for specific tasks, with the goal of improving the performance of LLMs is called *prompt engineering*. Effective [prompt engineering](/ai/playbook/technology-guidance/generative-ai/working-with-llms/prompt-engineering) can significantly improve the performance of LLMs on specific tasks. It's done by providing instructions and contextual information that help guide the model's output. Researchers can steer the LLM's attention toward the most relevant information for a given task by carefully designing prompts, leading to more accurate and reliable outputs.

In general, a well-designed prompt should contain the following information:

- **Role**: For example, if the LLM is expected to perform a customer service function, the prompt could include a system message such as: `You are a friendly AI agent who can provide assistance to the customer regarding their recent order.`.
- **System instructions**: Specific instructions that the LLM should follow. For example, `Provide the customer with the tracking information for their recent order.`
- **Examples**: Examples can help the LLM understand the task better. For example, `The tracking number for the order is a 7-digit number, such as 123-4567.`
- **Context**: Context can help the LLM understand the task better. For example, `The customer will need the shipping information and expected delivery date.`

A prompt might also use *Retrieval-Augmented Generation* (RAG). RAG is an architecture that augments the capabilities of an LLM by adding an information retrieval system that provides grounding data. This grounding data can be used to improve the quality of the generated text by providing information to the model. For example, a prompt might include a reference to a specific document or dataset that the model can use to generate a more accurate response.

If you intend to start with a source language prompt, then translate it for each target language, you shouldn't assume that just translating the prompt will be sufficient. Prompt translation is akin to translating marketing materials, in other words, [transcreation](../transcreation.md). While the translated prompt might be a good starting point, you'll need to repeat the prompt engineering process for each target language.

## Generating output in non-source languages

There are two general approaches when creating output from LLMs in languages other than the original language:

- Translate the prompt into the target language and have the LLM respond in that language.
- Use the source language prompt but ask the LLM to return the output in the target language.

Either approach might be most appropriate for your prompt, use case, and source/target language pair. Testing the output then becomes critical to ensuring the best chance of supporting your customers in their language.

For either approach, you should start with prompts that are globalized. Globalized prompts are designed to work across multiple languages and locales. They should be culturally neutral and avoid idiomatic expressions, slang, or other language-specific elements that might not translate well. Globalized prompts should also be clear and concise, providing the LLM with the necessary information to generate the desired output.

| Issue                        | Description | Recommendations |
| ---------------------------- | ----------- | --------------- |
| Ambiguous instructions       | Ambiguous prompts can lead to incorrect model responses. | Clarify the instructions in the prompts to ensure they're clear and unambiguous. Clear instructions help in eliminating confusion and lead to more accurate model responses. |
| Bias and stereotypes         | Biased prompts perpetuate stereotypes. | Avoid any content that might perpetuate stereotypes or display bias. Ensure that your prompts are impartial and respectful to all cultures. |
| Context dependency           | Prompts lacking context might confuse the model. | When creating prompts, provide relevant context to avoid any confusion. A lack of context might lead to misunderstandings and incorrect model responses. |
| Cultural references          | References specific to one culture might not translate well. For example, mentioning "Thanksgiving" in prompts might not be appropriate for international audiences. | Avoid using references that are specific to one culture. Instead, use universal references that can be understood by all cultures to ensure effective internationalization. |
| Cultural sensitivities       | Insensitive prompts might offend or misrepresent cultural norms. | Be mindful of cultural norms and sensitivities when creating prompts. Avoid any content that might be deemed offensive or insensitive. |
| Domain-specific vocabulary   | Lack of domain-specific terms can hinder task-specific prompts. | Make sure to adapt your vocabulary to include domain-specific terms, which help in creating task-specific prompts. |
| Formality levels             | Languages often have varying levels of formality (for example, formal vs. informal). | Choose prompts that align with the desired tone. Be aware of varying levels of formality in different languages and adapt your prompts accordingly. |
| Gender and pronouns          | Gendered pronouns and nouns vary across languages. Gender-neutral pronouns can work for English, but not for other languages. | Gender-neutral pronouns aren't universal, as not all languages have or accept gender-neutral pronouns. You might use gender-neutral pronouns for languages that support them, but you'll need to have separate prompts for languages that don't support them. |
| Hard-coded references        | Certain scenarios, like replying to sensitivities, system failures, or exceptions, require prompts to refer to specific pre-defined answers or error messages. | Avoid hard-coding messages in your prompts. Instead, have the model load them from a resource file external to your prompt. |
| Hard-coded user data         | Some prompts require you to pass pieces of information provided by the user, which could be in any language. You should avoid concatenating it with your prompt, since it would create a multilingual direct instruction. | Avoid concatenating user data with your prompt, instead make a call out to a separate section in your prompt that provides a data structure that includes the variables needed. |
| Idiomatic expressions        | Avoid using idiomatic expressions in prompts. For example: "the ball is in your court." | Avoid using idiomatic expressions in your prompts, as idiomatic expressions might not translate well across different languages. |
| Local context and references | Avoid including location or cultural-specific references (for example, famous landmarks, historical events) relevant to the target culture. | Avoid location or culture-specific references in your prompts. Instead, use universal references that can be understood by all cultures. |
| Numerical formats and units  | Different countries/regions use varying [date formats, measurement units, and numbering systems](../../locale/regional-settings.md). Adapt prompts to anticipate such differences. | Adapt your prompts to anticipate differences in date formats, measurement units, and numbering systems across different countries and regions. Evaluate the prompt response using the names of the country/region and language combination and [IETF BCP 47 locales](../../locale/standard-locale-names.md) to see which produces the most appropriate output for your use case. |
| Politeness conventions       | Some languages use specific markers to convey politeness or respect. | Include instructions in your prompts to handle politeness or respect conventions in different languages appropriately. |
| Sensitive language           | Some words or topics are taboo in certain cultures. For example, sensitive historical events or religious references | Avoid using words or topics that are taboo in certain cultures. Be mindful of cultural sensitivities when choosing the content of your prompts. |
| Spelling mistakes            | Spelling mistakes might create ambiguity or unexpected model responses. | Run spelling and grammar checks on your prompts before using them to avoid ambiguity or unexpected model responses. |
| Task specificity             | Generic prompts might not yield task-specific results. | Tailor your prompts for specific tasks to improve performance. Avoid using generic prompts that might not yield task-specific results. |
| Text delimiters              | Not all languages use the same text delimiters. | If your prompt includes adding text delimiters to the response, make sure that it accounts for variabilities. |
| Token count                  | For LLMs, the total token count limits include the model response. Non-Latin languages consume more tokens than Latin-based ones. | Make sure to account for the variability in token count between Latin-based and non-Latin languages. Don't set word count or token limits as a dependency or constraint in your prompt. |
| Tone and humor               | Humor and sarcasm might not translate well. For example, puns or wordplay are usually specific to a language. | Be cautious with prompts that rely on cultural humor or sarcasm, which might not translate well across different cultures. |

## Considerations for using AI-based features in global products

Keep the following considerations in mind when creating LLM prompts.  

### Region availability

You should ensure that the AI technology that you're planning to use is available in all the regions and for all the locales that you would like to support. Some AI technologies are subject to export restrictions and if these technologies are a critical component of your implementation then you might be limited to specific regions.

### Cross-border data flow and AI laws

Cross-border data flow is about the transfer of data across national borders, which is pivotal for global software development projects. Compliance with regional data protection laws and ensuring adequate computing resources are critical aspects that require meticulous planning and execution.

The computing resources that are hosting your LLMs might be in a different geography than other resources that you're using. Ensure that you're still compliant with regulations like the General Data Protection Regulation (GDPR) in Europe that can restrict data movement, aiming to protect privacy and national security.

The EU Artificial Intelligence Act includes stringent requirements for high-risk AI systems, adds another layer of complexity by imposing strict standards on data usage, transparency, and accountability. These regulations can pose challenges for AI development, as they require careful navigation to balance innovation with privacy and security concerns.
