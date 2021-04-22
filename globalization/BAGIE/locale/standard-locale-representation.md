# Standard locale representation

## Authoring notes

IETF BCP 47 - https://tools.ietf.org/html/bcp47

From wikipedia:
A single primary language subtag based on a two-letter language code from ISO 639-1 (2002) or a three-letter code from ISO 639-2 (1998), ISO 639-3 (2007) or ISO 639-5 (2008), or registered through the BCP 47 process and composed of five to eight letters;
https://www.iso.org/iso-639-language-codes.html
Up to three optional extended language subtags composed of three letters each, separated by hyphens; (There is currently no extended language subtag registered in the Language Subtag Registry without an equivalent and preferred primary language subtag. This component of language tags is preserved for backwards compatibility and to allow for future parts of ISO 639.)

- Highlight changes:  Yiddish “ji” changed to “yi”. Indonesian “in” became “id”. Hebrew “iw” became “he”. Serbo-croatian “sh” was replaced by Serbian “sr”, and Croatian “hr”. 

An optional script subtag, based on a four-letter script code from ISO 15924 (usually written in Title Case);
https://unicode.org/iso15924/iso15924-codes.html

An optional region subtag based on a two-letter country code from ISO 3166-1 alpha-2 (usually written in upper case), or a three-digit code from UN M.49 for geographical regions;
- Highlight changes CS -> RS and ME

Optional variant subtags, separated by hyphens, each composed of five to eight letters, or of four characters starting with a digit; (Variant subtags are registered with IANA and not associated with any external standard.)
Optional extension subtags, separated by hyphens, each composed of a single character, with the exception of the letter x, and a hyphen followed by one or more subtags of two to eight characters each, separated by hyphens;
An optional private-use subtag, composed of the letter x and a hyphen followed by subtags of one to eight characters each, separated by hyphens.

We should probably link to iso.org only

Provide examples.
