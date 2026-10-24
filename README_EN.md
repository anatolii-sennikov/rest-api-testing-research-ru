# rest-api-testing-research-ru

> [Russian version](README.md)

This repository contains unofficial Russian translations of research on REST API testing, along with neutral summaries.

Some time ago, I needed to dig into the theory, research, and current practices and approaches for a side project. Naturally, I wanted evidence and supporting arguments, too. As expected, the source material was available in English.

I'd gathered quite a few papers and other sources. I couldn't find any legally published Russian-language versions of these papers, but I knew there were people interested in the topic who find reading the English originals difficult. So I somewhat impulsively decided to create this repository.

As it turned out, producing decent translations takes more than one evening (although I'm still not sure mine are any good). There are conventions and established practices to consider. I had to choose between a more academic translation and a more informal, unofficial style—something closer to tech slang, with a fair number of anglicisms.

## Papers

| Paper | Year | Original license |
| --- | --- | --- |
| [SBFT 2026 Tool Competition: REST League](papers/sbft-rest-league/README.md) | 2026 | CC BY 4.0 |
| [AutoRestTest at the SBFT 2026 Tool Competition](papers/autoresttest-sbft-tool-competition/README.md) | 2026 | CC BY 4.0 |
| [WuppieFuzz: Coverage-Guided, Stateful REST API Fuzzing](papers/wuppiefuzz/README.md) | 2025 | CC BY 4.0 (preprint) |
| [Test Coverage in Microservice Systems: An Automated Approach to E2E and API Test Coverage Metrics](papers/microservice-test-coverage/README.md) | 2024 | CC BY 4.0 |
| [Microservice-Aware Static Analysis: Opportunities, Gaps, and Advancements](papers/microservice-aware-static-analysis/README.md) | 2023 | CC BY 4.0 |
| [Open Problems in Fuzzing RESTful APIs: A Comparison of Tools](papers/open-problems-fuzzing-restful-apis/README.md) | 2023 | CC BY 4.0 |
| [Deriving Semantics-Aware Fuzzers from Web API Schemas](papers/semantics-aware-fuzzers/README.md) | 2021 | CC BY 4.0 |
| [Automated Specification-Based Testing of REST APIs](papers/specification-based-rest-api-testing/README.md) | 2021 | CC BY 4.0 |

## Paper summaries

**SBFT 2026 Tool Competition: REST League**

The organizers compared five tools plus the RestTestGen baseline on 11 real-world REST APIs, using a common methodology: one hour per API, ten runs, defect detection, operation coverage, and code coverage. AutoRestTest performed best overall; no tool achieved more than 23% branch coverage.

**AutoRestTest at the SBFT 2026 Tool Competition**

The winning tool combines a dependency graph of semantic API properties, multi-agent reinforcement learning, and value generation using a large language model (LLM). Across 11 APIs, it found an average of 67.09 unique 5xx errors, compared with 24.65 for the runner-up.

**WuppieFuzz: Coverage-Guided, Stateful REST API Fuzzing**

An open-source fuzzer that uses an OpenAPI schema to build request sequences, mutate them, and guide the search using code coverage. It accounts for API state, testing sequences of calls rather than isolated requests. On Petstore, it covered 17–20 of 58 endpoints. The white-box configuration reached a coverage plateau sooner but did not improve final coverage.

**Test Coverage in Microservice Systems: An Automated Approach to E2E and API Test Coverage Metrics**

How can we measure which microservice endpoints are actually covered by E2E and API tests? The authors propose metrics and an automated approach based on source code and execution traces. On TrainTicket (41 microservices and 262 endpoints), API tests covered 91.98% of endpoints, E2E tests covered 45.42%, and combined coverage was 92.36%.

**Microservice-Aware Static Analysis: Opportunities, Gaps, and Advancements**

Why does conventional static analysis struggle with distributed systems implemented in different languages, and how can it be made to account for inter-service calls, dependencies, and architectural degradation? The prototypes identify components with precision and recall above 95% and detect 11 types of microservice code smells.

**Open Problems in Fuzzing RESTful APIs: A Comparison of Tools**

Seven fuzzers were compared on 19 real-world REST APIs and one synthetic API with injected defects, using actual line coverage as the metric. EvoMaster (56.8% on average) and Schemathesis (54.5%) performed best, but no black-box fuzzer exceeded 60% line coverage. Analysis of logs and source code identified six categories of unresolved challenges: authentication, databases, external services, schema mismatches, string constraints, and unreachable code.

**Deriving Semantics-Aware Fuzzers from Web API Schemas**

Can an OpenAPI or GraphQL schema be used to build a fuzzer that checks not just data formats but also response semantics—for example, status codes, headers, schema conformance, and information leaks? Schemathesis found 1.4–4.5 times as many unique defects as the best-performing alternative and was the only tool to find defects in four services.

**Automated Specification-Based Testing of REST APIs**

Can a REST API be tested using only an OpenAPI 3.x specification, without access to the source code? The method generates and executes test cases in four modes, ranging from fully automated to user-assisted. Across a set of 30 APIs, it generated between 1,222 and 3,807 test cases.

## Structure

```text
.
├── README.md          # purpose, paper catalog, summaries, and principles
├── LICENSE.md         # text of the CC BY 4.0 license
├── ATTRIBUTION.md     # licensing, attribution, and translation rules
└── papers/
    └── <slug>/
        ├── README.md        # paper overview
        ├── <slug>-ru.md     # Russian translation
        └── images/          # illustrations
```

## Ethical baseline

1. **Meaning and fidelity.** We don't add conclusions, gloss over weaknesses, or "improve" the author's claims. Faithful translation doesn't have to be literal, but it must not put words in the author's mouth.

2. **Anything not in the original.** Explanations of terms or context, comments on errors, caveats, disagreements, and added emphasis must be marked—for example, with brackets, footnotes, or a "Translator's note." Readers should be able to distinguish the author's content from the translator's additions. But applying "not in the original → square brackets" mechanically doesn't work: the result would be a text cluttered with square brackets. We mark additions that affect meaning, not every comma.

3. **Errors and questionable details.** An error or questionable detail in a formula, number, code snippet, or claim may be left as it appears in the original or corrected—but any correction must be explicitly marked, for example in a footnote stating "The original reads: …". The translator must not replace the author's actual words with a guess about what the text should have said. Minor typos in prose may be corrected without annotation. Contacting the author can help verify an error or typo and clarify terminology. This is neither a licensing requirement nor a prerequisite; it is simply good practice.

4. **Responsibility for the translation.** Responsibility for the translation's content rests with the translator, including when machine translation (MT) or an LLM is used—not with the model or the original author. If MT/LLM was used, disclose this in a "Translation preparation" line in the translation header.

5. **Conflicts of interest.** Any financial, professional, competitive, or personal relationships with the authors or their competitors that could affect—or appear to affect—the choice of paper, wording, or commentary must be disclosed in the translation header or an accompanying file. The fact that a paper's topic overlaps with one's own research area is not, by itself, a conflict of interest.

6. **Author notification.** If the license permits translation and publication, notifying the author is a courtesy and good practice.

7. **Rights and licensing.** Three separate things must be distinguished: the source's license and status, the legal basis for publishing the translation, and the license that applies to the translation itself. The first two are documented on the paper page; the third is stated in the translation header. See [ATTRIBUTION.md](ATTRIBUTION.md) for details and [LICENSE.md](LICENSE.md) for the full license text. The translation is unofficial; if anything differs, the original takes precedence.

## Licensing and attribution

© 2026 A. N. Sennikov. Unless a paper page or translation header states otherwise, materials created for this project are licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). Rights to the original papers, images, and trademarks remain with their respective rights holders. For attribution rules and translation conditions, see [ATTRIBUTION.md](ATTRIBUTION.md); the full license text is available in [LICENSE.md](LICENSE.md).
