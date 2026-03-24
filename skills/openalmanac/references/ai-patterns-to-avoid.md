The following is an abridged version of an article on Wikipedia covering signs of AI writing (https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing)
## AI Writing Patterns to Avoid

LLMs produce recognizable patterns. These patterns erode reader trust and trigger automated detection. This document is a field guide — learn the patterns so you don't produce them.

### Why these patterns exist

LLMs predict the statistically most likely next token. This causes regression to the mean: specific, unusual facts get smoothed into generic, positive-sounding language that could apply to almost anything. A precise detail like "invented the first train-coupling device" becomes "a revolutionary titan of industry." The subject gets simultaneously less specific and more exaggerated.

LLMs also have repetition penalties that cause unnecessary synonym rotation, and they are trained heavily on promotional text (press releases, marketing copy, fan wikis, listicles), which biases output toward puffery even when the prompt asks for neutrality.

Every pattern below is drawn from real articles flagged as AI-generated.

---

## Content Patterns

### Inflating significance

Sentences that announce how important, pivotal, or enduring something is — without providing evidence for that importance.

This is the single most common AI tell. LLMs attach these statements to almost anything, including mundane facts like population data or etymology.

Phrases that signal this pattern:

- "stands as / serves as a testament to"
- "a vital / significant / crucial / pivotal / key role / moment"
- "underscores / highlights its importance / significance"
- "reflects broader trends"
- "symbolizing its ongoing / enduring / lasting"
- "setting the stage for / marking / shaping the"
- "represents a shift / key turning point"
- "evolving landscape"
- "indelible mark"
- "deeply rooted"

Bad:

> The Statistical Institute of Catalonia was officially established in 1989, marking a pivotal moment in the evolution of regional statistics in Spain. The founding of Idescat represented a significant shift toward regional statistical independence. This initiative was part of a broader movement across Spain to decentralize administrative functions and enhance regional governance.

The first sentence states a fact. The next two sentences say nothing — they just announce that the fact is important, using three different phrasings. Remove them.

Bad:

> This etymology highlights the enduring legacy of the community's resistance and the transformative power of unity in shaping its identity.

This is editorial commentary attached to an etymology. The word origin doesn't "highlight" anything. State the etymology and stop.

Fixed:

> The name Bakunutan was hispanized to Bacnotan during the Spanish colonial period. The modification appears in official documents preserved in the National Archives in Manila.[@archives-bacnotan-records]

When writing about biology, ecology, places, or cultural heritage, this pattern manifests as overemphasis on ecosystem connections, conservation importance, or cultural significance — even when those connections are tenuous or generic.

Bad:

> Preserving this endemic species is vital not only for ecological diversity but also for sustaining the cultural traditions connected to Hawaii's native flora.

If no source makes this claim, don't make it. State the species' classification, range, and conservation status if known.

### Superficial analysis

Present participle phrases ("-ing" clauses) appended to facts, claiming to interpret what those facts mean.

- "highlighting his importance in the field"
- "reflecting her dedication to teaching"
- "underscoring their influence"
- "demonstrating his expertise"
- "showcasing her contributions"
- "ensuring continued relevance"
- "fostering a sense of connection"
- "contributing to the socio-economic development of the region"

These are unattributed editorial opinions dressed up as natural consequences. Facts don't "highlight" or "reflect" — only people can.

Bad:

> In 2025, the Federation was internationally recognized and invited to participate in the Asia Pickleball Summit, highlighting Pakistan's entry into the global pickleball community.

Fixed:

> In 2025, the Federation was invited to the Asia Pickleball Summit.[@dawn-pickleball-summit]

The fix removes the interpretive clause entirely. The fact speaks for itself.

Bad:

> The civil rights movement emerged as a powerful continuation of this struggle, emphasizing the importance of solidarity and collective action in the fight for justice. This historical legacy has influenced contemporary African-American families, shaping their values, community structures, and approaches to political engagement.

Every clause after the first comma is unsourced analysis. Two sentences, zero information.

### Promotional language

LLMs skew positive. Even when prompted for neutral, encyclopedic tone, output drifts toward advertisement copy. This happens both when generating new text and when rewriting existing text — LLMs often insert promotional language while claiming they removed it.

Words and phrases that signal this:

- "boasts a," "vibrant," "rich" (figurative), "profound"
- "enhancing," "showcasing," "exemplifies"
- "commitment to," "natural beauty"
- "nestled," "in the heart of"
- "groundbreaking" (figurative), "renowned"
- "diverse array," "dynamic hub," "thriving community"
- "seamlessly," "captivates," "breathtaking"

Bad:

> Nestled within the breathtaking region of Gonder in Ethiopia, Alamata Raya Kobo stands as a vibrant town with a rich cultural heritage and a significant place within the Amhara region. Alamata Raya Kobo offers visitors a fascinating glimpse into the diverse tapestry of Ethiopia.

Fixed:

> Alamata Raya Kobo is a town in the Amhara region of Ethiopia, located in the Gonder area.[@britannica-alamata-raya]

One sentence replaces an entire promotional paragraph — and contains more useful information (the actual location).

### Vague attribution

Attributing claims to unnamed authorities instead of citing specific sources. This is weasel wording.

- "Industry reports suggest"
- "Observers have cited"
- "Experts argue"
- "Some critics argue"
- "Several sources / publications" (when only one or two are cited)
- "Researchers treat X as"
- "Efforts are ongoing to"
- "Due to its unique characteristics, X is of interest to researchers"

Bad:

> The Kwararafa confederacy is described in scholarship as a shifting Benue valley coalition. Modern researchers treat Kwararafa as a fluid political and cultural formation rather than a fixed state.

Which scholarship? Which researchers? Name them, or cite them, or don't make the claim.

LLMs also exaggerate the breadth of agreement. They present one source's view as widely held, mention multiple "scholars" while citing a single person, or imply lists are non-exhaustive when sources give no such indication.

Bad:

> The band's rise has often centered on Zardoya's bilingual lyrics, which several publications have cited as "bridging worlds through music."

The two citations attached to this sentence are a Los Angeles Times profile and a Time Magazine article. Two sources is not "several publications."

### Empty evaluative sentences

Sentences that fill space without adding information.

**Generic role statements** — announcing categories without specifics:

Bad: "Sharma has held roles applying machine learning in finance and geographic information systems."

What roles? What did he build? When? Either provide specifics or don't mention it.

Fixed: "At DronaMaps, Sharma built a geocoding server based on OpenStreetMap.[@dronamaps-geocoding]"

**Evaluative connectors** — editorial commentary masquerading as transitions:

- "These themes are reflected in his work"
- "This interest would later shape her career"
- "His contributions demonstrate a commitment to excellence"

These are opinion. Remove them. Let facts establish their own connections.

**Capability announcements** — sentences that announce a list is coming:

Bad: "Across his research and industry roles, Sharma has demonstrated expertise in several areas of machine learning:"

The list that follows is the content. The announcement adds nothing. Delete it and start with the list.

### Formulaic conclusions

A rigid formula: "Despite [positive qualities], [subject] faces challenges including [list]. Despite these challenges, [vaguely optimistic statement]." Often appears as a "Challenges" or "Future Outlook" section at the end of an article.

Bad:

> Despite its industrial and residential prosperity, Korattur faces challenges typical of urban areas, including... With its strategic location and ongoing initiatives, Korattur continues to thrive as an integral part of the Ambattur industrial zone.

Bad:

> Despite their promising applications, pyroelectric materials face several challenges that must be addressed for broader adoption. Despite these challenges, the versatility of pyroelectric materials positions them as critical components for sustainable energy solutions.

Encyclopedic articles don't need conclusions. They don't need to end on an optimistic note. End with the last substantive fact.

### Knowledge-gap hedging

Disclaimers about incomplete information, often paired with speculation about what the missing information "likely" contains.

- "While specific details are limited..."
- "Though not widely documented..."
- "Based on available information..."
- "Information about X is not extensively documented in readily available sources, but..."
- "[Person] keeps much of their personal life private"

Bad:

> While specific information about the fauna of Studniční hora is limited in the provided search results, the mountain likely supports a range of alpine and subalpine species.

If you don't have information, don't write the sentence. Don't speculate about what might be true and don't explain why you don't know. Either find a source or omit the claim.

### Overattribution of media coverage

Listing sources that covered a subject as evidence of the subject's importance, often without summarizing what those sources actually said.

Bad:

> She spoke about AI on CNN, and was featured in Vogue, Wired, Toronto Star, and other media. Her insights have also been featured in Wired, Refinery29, and other prominent media outlets.

This tells the reader nothing about what she said or what those outlets reported. It just name-drops publications.

In Almanac articles, cite sources. Summarize what those sources report. Don't use the body text to list which outlets have covered the subject.

---

## Language Patterns

### AI vocabulary

Specific words appear at dramatically higher rates in LLM output than in human writing from before 2023. One or two may be coincidental. A cluster of them in the same passage is one of the strongest tells.

**High-frequency AI words:** delve, tapestry (figurative), landscape (figurative), intricate / intricacies, meticulous / meticulously, pivotal, crucial, vibrant, underscore (verb), testament, enduring, bolstered, fostering, garner, showcase, interplay, enhance, align with, valuable

These words co-occur. Where there is one, there are usually several more.

Bad:

> Somali cuisine is an intricate and diverse fusion of a multitude of culinary influences, drawing from the rich tapestry of Arab, Indian, and Italian flavours. Additionally, a distinctive feature of Somali culinary tradition is the incorporation of camel meat and milk, cherished and fundamental elements in the rich tapestry of Somali cuisine. An enduring testament to the influence of Italian colonial rule is the widespread adoption of pasta in the local culinary landscape, showcasing how these dishes have integrated into the traditional diet. Additionally, Somali merchants played a pivotal role in the global coffee trade.

Words flagged in that passage: intricate, tapestry (twice), additionally (twice), enduring, testament, landscape, showcasing, pivotal. That density is unmistakable.

Fixed:

> Somali cuisine draws on Arab, Indian, and Italian influences.[@britannica-somali-cuisine] Camel meat and milk are staple foods.[@fao-somali-livestock] Pasta and lasagne entered the diet during the Italian colonial period and remain common, particularly in the south.[@guardian-somali-food] Somali merchants were among the first to export coffee beans.[@smithsonian-coffee-origins]

Four sentences. Four facts. Four citations. No filler.

### Copula avoidance

LLMs systematically avoid "is" and "are," substituting more elaborate constructions.

- "serves as" instead of "is"
- "stands as" instead of "is"
- "holds the distinction of being" instead of "is"
- "features" or "boasts" instead of "has"

Bad: "Gallery 825 serves as LAAA's exhibition space for contemporary art. The gallery features four separate spaces."

Fixed: "Gallery 825 is LAAA's exhibition space for contemporary art. The gallery has four separate spaces."

This pattern is especially visible in AI copyedits, which will "improve" prose by replacing simple verbs with elaborate ones.

### Negative parallelisms

Formulaic constructions that create artificial contrast or false balance.

- "Not only X, but also Y"
- "Not just X, but Y"
- "It's not just about X, it's about Y"
- "X, however, is not just Y — it's Z"
- "No X, no Y, just Z"

Bad: "Not only a professor, but also a researcher."

Being a professor and a researcher aren't contrasting activities. Use a straightforward statement.

Fixed: "Smith is a professor at MIT and has published research on X.[@mit-faculty-smith][@nature-smith-research]"

### Rule of three

LLMs overuse groups of three — "adjective, adjective, and adjective" or "short phrase, short phrase, and short phrase" — to make superficial points appear comprehensive.

Bad: "The event features keynote sessions, panel discussions, and networking opportunities."

Bad: "Her work explores identity, memory, and belonging."

These triplets are almost always generic enough to describe anything in their category. If the three items don't add specific information, cut the sentence.

### Excessive synonym rotation

Cycling through different terms for the same subject within a few sentences, driven by the repetition penalty.

Bad: "The professor... the researcher... the educator... the expert... the scholar..."

Use the subject's name, then pronouns. After introducing "Dr. Jane Smith," use "Smith" or "she." Don't invent new descriptors each sentence.

### Em dash overuse

LLMs use em dashes more frequently than human writers and use them where commas, parentheses, or colons would be more natural. They tend toward a punched-up, sales-pitch cadence.

Bad:

> The term is primarily promoted by Dutch institutions — not by the people themselves. You don't say "Netherlands, Europe" — yet this mislabeling continues.

Occasional em dashes are fine. Three or more per paragraph, or em dashes used in every other sentence across a passage, is a pattern.

### False ranges

"From X to Y" where X and Y aren't endpoints on a coherent scale.

Bad: "From teaching to research to outreach" — this is a list, not a progression.

Bad: "His contributions span from groundbreaking publications to innovative teaching methods" — there is no scale here.

Valid: "From 1990 to 2000" (temporal). "From Assistant Professor to Full Professor" (hierarchical).

Use a plain list instead. "Her work includes education, research, and public outreach."

---

## Structural Patterns

### Publication lists as bibliographies

Articles are not CVs. Never include bulleted or formatted bibliographies.

Bad:

> - Mehta, M., & Shao, C. (2023). A Greedy Agglomerative Framework... IEEE Transactions on Industrial Informatics, 19(12), 11856-11867.

Discuss publications narratively — what question the research addressed, what was found, why it matters.

Fixed: "In 2023, Mehta and Shao proposed a greedy agglomerative framework for clustered federated learning, addressing heterogeneous data distributions across manufacturing sites.[@ieee-mehta-federated]"

### Repetition across sections

The same fact appearing in multiple sections with no new detail.

Bad:

> Lead: "joined MIT in 2015 as Assistant Professor [@mit-faculty-smith]"
> Career section: "In 2015, Smith joined MIT as Assistant Professor [@mit-faculty-smith]"

Each section should add new information. If you stated a fact in the lead, the later section should expand on it — not restate it.

### Citation placement

Citations go after punctuation, not before. The period (or comma, or other mark) closes the sentence; the citation attaches to it.

Bad: `...preserved in the National Archives in Manila [@archives-bacnotan-records].`

Fixed: `...preserved in the National Archives in Manila.[@archives-bacnotan-records]`

Bad: `...staple foods [@fao-somali-livestock]. Pasta and lasagne...`

Fixed: `...staple foods.[@fao-somali-livestock] Pasta and lasagne...`

### Unnecessary tables

LLMs create small tables for information that works better as prose. A two-row, two-column table is almost never the right format.

---

## The Core Test

Read each sentence you write and ask: does this sentence contain a specific fact that the reader didn't know before? If the answer is no — if the sentence interprets, evaluates, announces, puffs up, or summarizes without adding information — delete it.

Good Almanac articles are dense with facts and light on commentary. Every sentence earns its place by telling the reader something new and sourced.
