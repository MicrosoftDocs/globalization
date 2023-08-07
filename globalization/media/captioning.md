---
title: Captioning and subtitling
description: Captioning can be employed to make videos useful to an international audience and users with disabilities.
author: m-kauppinen
ms.author: v-mikau
ms.topic: conceptual #Required; leave this attribute/value as-is.
ms.date: 07/12/2023

---

# Captioning and subtitling

It’s not uncommon for people to talk about captioning and subtitling as if they were the same thing. They are two different processes, however, even though both are about displaying text on the screen.

Captioning is primarily made for viewers who are deaf or hard of hearing. In addition to transcribing the dialog, captions also describe non-speech audio, for example, when a song or sound effect is playing. In this way the viewers get a better understanding of the content without hearing it. Captioning comes in two styles: closed captioning, which is hidden until the viewer activates it, and open captioning, which is always visible.

In the US, closed captions are mandatory for all public multimedia such as news or commercials. The Federal Communications Commission requires video programming providers, such as TV networks, offer closed captions for all new programs which have audio in English or Spanish, with certain exemptions. For the complete details, refer to [Title 47 CFT 79.1 Closed captioning of televised video programming](https://www.ecfr.gov/current/title-47/chapter-I/subchapter-C/part-79/subpart-A/section-79.1). Additionally, the Americans with Disabilities Act (ADA) requires that businesses that are open to public such as hospitals, hotels, and shopping centers provide access to verbal information on televisions, films or slide shows. Captioning is one way of fulfilling this requirement. For the complete details, refer to [Americans with Disabilities Act Title III Regulations](https://www.ada.gov/law-and-regs/title-iii-regulations/).

Subtitling displays a translation of the dialogue so that people who have limited or no knowledge of the original spoken language can follow the content. It does not describe any other audible content the way captioning does. Subtitled content, such as a TV show from a streaming service or a film on DVD, is often available in multiple languages from which the viewer can choose.

Captioning and subtitling also make it possible to understand the content by reading if the viewer needs to turn the volume down for some reason, or if spoken dialogue is hard to hear because of background noise.

Both captioning and subtitling are less expensive to implement than voice-over, dubbing or a full re-creation of the content. For more information on those, refer to [Re-creation](re-creation.md).

Some systems and services include automatic multimedia captions created by speech to text technology. They are better than no captions, but generally are of much lower quality than professionally created captions.

## Technical considerations

Captioning and subtitling share certain limitations inherent in displaying text on screen and making it readable.

- Viewers have limited time for reading each caption. There is no hard and fast guideline for this, but around 5 seconds seems common.
- Screen space is limited. To avoid covering up too much of the multimedia content, typically no more than two lines of text are displayed. The maximum number of characters per line depends on the exact technology that is used, but around 40 is a common limit. This is also tied to the timing limitation: viewers can only read so many lines in a few seconds.

As a result of these limitations, captions and subtitles should have their own style guides. Using different (shorter) terms, using abbreviations, and removing some punctuation can save some characters.

## Creating subtitles

Here is an overview of how the process of creating subtitles for an existing video could go:

1. Create a source language script. There are tools that can do this automatically, such as Azure Media Services. Alternatively, you might have access to the original script.
1. Review the script against the source video and correct it as necessary. Automatically generated scripts should always be checked by a human, and even original scripts might have changed during the production of the video. Check for things like technical correctness, grammar, terminology, and spelling. This way the subtitles can correct for errors that might have crept into the source video.
1. Translate the script. If you have a style guide for subtitling, the translation can already benefit from it at this stage.
1. Review the translation for correctness against the video and correct it as necessary.
1. Create the subtitles from the translated script, keeping in mind the limitations mentioned under [Technical considerations](#technical-considerations) and referring to the style guide to help you shorten the text. Subtitles will almost always be a condensed version of what is said on the video. If your source language script contains timestamps for the audio, it can help reduce the need for adjustments in the next step.
1. Insert the subtitles into the video and validate the result, adjusting their context, timing, and length as needed to compensate for the technical limitations.
