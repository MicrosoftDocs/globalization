This documentation is archived and is not being maintained.

# Telephone Number

Like addresses, the format for telephone numbers around the world varies significantly. Once again, input fields and the routines that process information dealing with telephone numbers should be able to handle the variety of formats.

Formats for telephone numbers for selected countries:

**Country**
**Format**
China
1234 5678
France
01-23-45-67-89
Poland
\(12) 345.67.89
Singapore
123 4567
Thailand
\(01) 234-5678 or
(012) 34-5678
United Kingdom
0123 456 7890 or
01234 567890
United States
[(123) 456 7890[![](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABAAAAAQCAYAAAAf8/9hAAABcklEQVR4XpXTPUvDUBTH4aR2c2hBQXGpTiIORhBcBOvgYKf0Awi+4Ggr1MVPIIrYdnEpShddHIyLi6AVXVxsRRDRwbi4KNgu4lCIv8i/i6QRDzycy+09555LqOl5nhEUptPoJe1iDHU8oYlrlDw79m4QEbSLPexzsIc8hDRm8YBjLpj4q8EgxQdab+MNd4ghhQ2adIc1+ORAFEnWWfTDRp7GDfImlsIavKALLuqoqMGUCs4wHtagiQ5uc8kDyCOBKlP1k78QNTOZnMXCQRxWsbjl6iuskV41SQG2Gj9rikvcR1WcgKFDBa1LOEUK56hqv8BUFV3SGWkVS9JQ6Dsv4wQ1DKMPORUvkm78BhdQMI1CTa5I0yrcwSFqFD+SZ7DQesIkCG5S/JpkHYERQRmuNsrZ7Grc+Ef8/Bcoslkfae8Wc7CUHZ++TuAEBj86pHntjaDKXllPy6PW/gkKFaThwp/K87N8hDcQTTKKFTioSxqB8Q2BNX5JtAljwgAAAABJRU5ErkJggg== "Call: (123) 456 7890")](# "Call: (123) 456 7890")]
Notice that there are different separators such as hyphens (-), periods (.), and spaces, different groupings (two, three, four, five, and six digits per group), and different numbers of total digits used (7-11). Also, the examples just given didn't include country codes, which could be anything from one to three digits.

The ITU-T standard E.164, defined by the Comité Consultatif International Téléphonique et Télégraphique (CCITT), states that the maximum number of digits is 15, but this doesn't include space for things like:

-   Long-distance access codes
-   Passwords
-   Credit card numbers
-   Extensions

When designing and coding for display and storage of telephone numbers, do not assume one given format, but leave it very flexible. The current implementation of NLS APIs and the .NET Framework do not provide any telephone-number formatting information. Knowing this, you should:

-   Keep country codes, area codes, and phone numbers in separate fields.
-   Do not expect a fixed number of digits for an area code or phone number. (A phone number can be anything between 4 to 11 digits.)
-   Do not expect mobile and landline phone numbers to have the exact same format in all markets.
-   Expect different separators-hyphens (-), periods (.), and commas (,)-between numbers. (You will need to do your own parsing for these separators.)

[Show:]{} Inherited Protected
