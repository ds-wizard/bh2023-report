---
title: 'Building Towards a Machine-Actionable Software Management Plan: A BioHackathon Europe 2023 Report'
tags:
  - Software Management
  - Software Management Plan
  - SMP
  - Machine-Actionable
  - GitHub
  - Research Software
authors:
  - name: Marek Suchánek
    orcid: 0000-0001-7525-9218
    affiliation: 1
  - name: Vojtěch Knaisl
    orcid: 0000-0003-0103-8468
    affiliation: 1
  - name: Renato Alves
    orcid: 0000-0002-7212-0234
    affiliation: 2
  - name: Eva Martin del Pico
    orcid: 0000-0001-8324-2897
    affiliation: 3
affiliations:
  - name: Faculty of Information Technology, Czech Technical University in Prague
    index: 1
  - name: European Bioinformatics Institute (EMBL-EBI)
    index: 2
  - name: Barcelona Supercomputing Center (BSC)
    index: 3
date: 3 November 2023
bibliography: paper.bib
group: \#8 SMW + maSMPs
authors_short: M. Suchánek, V. Knaisl, R. Alves, and E. Martin del Pico
git_url: https://github.com/ds-wizard/bh2023-report
event: BH2023
---

# Abstract

This report provides an overview of our activities and accomplishments concerning machine-actionable Software Management Plans (SMPs) and the Software Management Wizard (SMW) during the ELIXIR BioHackathon Europe 2023. ELIXIR acknowledges the critical role of effective software management in facilitating sustainable and reproducible research outcomes. The Software Best Practices group is actively committed to establishing a robust framework for SMP creation. In this project, our primary focus is on streamlining the SMP creation process for research software within ELIXIR. To achieve this, we are working on developing essential integrators and identifying and reviewing the relevant metadata schema. This effort is closely aligned with various related initiatives such as OpenEBench, FAIR4RS, RDA, maSMPs, among others. The outcomes of the BioHackathon project are now available for immediate use and can be further refined in the future based on community feedback and advancements in research software best practices.

# Introduction

In recent years, the management of research software has garnered increasing attention across various domains. This heightened interest has given rise to a myriad of approaches and services aimed at addressing the unique challenges of this crucial aspect of scientific research. Notable developments in this landscape include initiatives like Codemeta, Software Heritage, the introduction of machine-actionable Software Management Plans (SMPs), and the proliferation of best practices and templates within research infrastructures.

ELIXIR has recognized the importance of proper software management and the adoption of SMPs to facilitate reproducibility and sustainability in research. To further these objectives, ELIXIR established its Software Best Practices group, which has been diligently working on creating an SMP template. This template serves as a foundation for structuring software management plans and streamlining the process of their creation. A significant milestone in this endeavor was the encoding of this SMP template as a knowledge model within the [Data Stewardship Wizard (DSW)](https://ds-wizard.org) platform [@dswPaper]. This transformation resulted in the creation of the Software Management Wizard (SMW), a user-friendly tool that empowers the research community to readily engage with SMPs and enhance their software management practices.

This project builds upon these foundations, addressing both content and technical aspects. It involves refining the SMP template by improving its structure, questions, and machine-actionability. Additionally, the project aims to align the template with pertinent ontologies and metadata schemas to ensure seamless interoperability and adherence to recognized standards. Simultaneously, the technical aspects of efficiently composing and utilizing SMPs are being enhanced, further bolstering the capabilities of the research community in their software management endeavors. Through these combined efforts, this project seeks to foster greater transparency, reproducibility, and efficiency in research software management within the ELIXIR community and beyond.

# ELIXIR SMPs, maSMPs, and SMW

The ELIXIR Software Best Practices group (under the Tools Platform) aims to improve the quality and sustainability of Life Science research software. Among the goals is to consolidate software management planning, provide relevant training/guidance, and other means to enable adoption of software development best practices. Over the years, the group developed a template for SMPs which has been later on turned into a knowledge model for DSW, resulting in the Software Management Wizard (SMW). Inspired by other relevant activities in the field of machine-actionable DMPs and SMPs, the group has been focusing machine-actionable SMPs in the recent period.

## Existing Mapping

In prior workshops, the knowledge model (KM) and its associated queries were meticulously aligned with various ontologies, including ELIXIR SMP [@elixirSMP], [RDMO SMP](https://rdm.mpdl.mpg.de/2022/12/09/smp-template-available/), maSMP Ontology [@masmpOntology], Bioschemas ([Computational Tool Profile](https://bioschemas.org/profiles/ComputationalTool/1.0-RELEASE)), and [CodeMeta](https://codemeta.github.io/). This mapping process involved linking 30 KM questions to specific properties, predominantly drawing from the groundwork laid by ELIXIR SMP [@elixirSMP]. For instance, it revealed that the property `discussionURL` could aptly address the question *Do you state how to report bugs and/or usability problems by the software user/s?*.

Building upon this foundational mapping, an expanded effort was undertaken to map all KM questions and explore potential machine-actionable representations of corresponding responses. In this endeavor, 56 KM questions were scrutinized, leading to the identification of 47 properties sourced from [schema.org](https://schema.org), [bioschemas.org](https://bioschemas.org), maSMP Ontology [@masmpOntology], and [NCI Thesaurus (NCIt)](https://ncit.nci.nih.gov/ncitbrowser/). This comprehensive mapping initiative marks a significant stride towards enhancing the interoperability and semantic richness of the KM.

## Aligning Knowledge Model

During the reevaluation of the mapping process, the knowledge model underwent iterative refinement through collaborative discussions within a broader group. Notably, improvements were made to the formulation of certain questions, exemplified by the adoption of a *list question* approach. This departure from requiring a list of items in a single field, presented as a string with commas, contributes to a more user-friendly and versatile design.

The collaborative discussions also served as a platform for addressing additional issues that emerged, sparking further enhancements to the knowledge model. An instance of such refinement involved diversifying the available versioning schemes. Initially, the questions exclusively endorsed [Semantic Versioning (SemVer)](https://semver.org), overlooking alternative and often more fitting schemes such as [Calendar Versioning (CalVer)](https://calver.org/). This realization prompted a broader consideration of versioning practices, enriching the knowledge model's adaptability to diverse development scenarios and preferences.

## Suggestions for maDMPs

Despite the substantial updates made to the knowledge model during the BioHackathon, there remain several crucial steps yet to be taken for the continuous enhancement of maSMPs. Notably, the following suggestions have been identified as key areas for improvement:

1. **Alignment with CodeMeta**: A priority lies in aligning maSMPs more closely with [CodeMeta](https://codemeta.github.io/), a widely adopted standard for machine-readable (research) software metadata. This alignment ensures a seamless integration of maSMPs into the broader ecosystem of machine-readable software metadata, fostering interoperability and standardized representation.

2. **Contributor Alignment with CITATION.cff**: To streamline the contribution process, aligning maSMPs with [CITATION.cff](https://citation-file-format.github.io/) is recommended. Given the widespread usage of CITATION.cff, this alignment facilitates a more standardized and widely accepted approach to acknowledging contributors, thus enhancing the overall transparency and attribution of contributions.

3. **Enhancement of Questions and Machine-Actionability**: A targeted effort should be directed towards improving the questions within maSMPs, particularly in areas such as documentation, versioning, requirements, and dependencies. This involves refining the machine-actionability of these aspects to ensure that responses can be effectively processed and utilized in automated workflows, promoting a more efficient and reliable exchange of software-related information.

By addressing these areas, maSMPs can further solidify their utility, align with established standards, and contribute to a more seamless integration within the broader landscape of machine-readable software metadata. These steps will not only enhance the comprehensiveness of the knowledge model but also promote its broader adoption and usability in diverse research and software development contexts.

# SM Wizard Enhancements

The technical aspect of our project focused on providing a way to use an existing maSMP to (pre)fill a questionnaire in SMW and also vice versa to generate a maSMP from existing questionnaire and publish it, e.g. in a GitHub repository (attach it to the research software project). In order to do that, we used the mapping between the ontology and the SMP knowledge model to create an SMP Importer and SMP Document Template. For the publishing of an SMP, a submission service has been developed.

![Diagram of SMW Imports and Exports](./figures/smw-diagram.png)

## SMP Importer

DSW offers so-called *project importers*, a configured external service that opens as a pop-up child window from a questionnaire, gets basic information about the project, user can interact with the window in any way (e.g. select something, upload file, fill a form), and finally it returns back a set of replies back to the questionnaire and closes. In technical view, it is implemented through the [DSW Importer SDK](https://github.com/ds-wizard/dsw-importer-sdk), a JavaScript library; however, the service can also have its own backend and further integrations. In this way, it provides high level of flexibility in matter of getting multiple replies from basically any source to DSW.

We developed such an importer for maSMPs in RDF, more specifically in JSON-LD. Once the importer window opens, the user can provide maSMP in three ways:

- upload a file directly,
- provide a URL to the file,
- fill owner, repo name, and file path in case of public GitHub repository.

Upon the action, the file is loaded and processed on the backend (in Python, via AJAX), and a set of replies is sent back to the questionnaire in SMW where the user can review what is being imported and accept it or reject it. The backend has two main tasks. First, it gets the RDF/JSON-LD contents from the desired resource (e.g. from file, downloads from URL, or tries to fetch from GitHub via API). Second, it encodes the mapping and translated from RDF/JSON-LD to questionnaire replies; more specifically to instructions what should be pushed back to SMW. When this is done, the result is returned to the frontend/JavaScript which sends it back through the SDK to SMW (and closes the importer window).

![Options of SMP Importer](./figures/smp-importer.png)

The SMP Importer is publicly available on GitHub under Apache-2.0 license and is ready for use as well as further enhancements in the future. Here again, it can be extended in terms of mapping (change of SMP questions, new information in SMPs, etc.) as well as supported ways how to get maSMPs or their supported formats.

## SMP Document Template

In order to update the research software metadata in a GitHub repository, it is necessary to convert the questionnaire back into the format compatible with SMP Importer. The DSW provides a solution through the creation of a Document Template that covers the mapping process. Technically, the Document Template is implemented as a Jinja template. The DSW provides to the Document Template a context containing the Knowledge Model, questionnaire, and questionnaire responses.

Users are granted the flexibility to choose their preferred output format (such as HTML, JSON, RDF, etc.), and they can define the specific structure of the Document Template using Jinja. Subsequently, DSW utilizes this Document Template to generate the appropriate document, tailored to the chosen format.

We developed such [a document template](https://github.com/ds-wizard/masmp-template) for research software metadata. This template generates a JSON-LD output that can be placed to the GitHub Repository. It's important to note that the current version of the document template only encompasses a portion of the Knowledge Model, specifically Chapter 1 and Chapter 6. This is because the mapping process for the remaining parts of the Knowledge Model is still ongoing. Our future efforts will be directed towards completing the mapping for the entire Knowledge Model.

![Preview of maSMP in SMW](./figures/smp-document.png)

The SMP Document Template is accessible to the public via [GitHub](https://github.com/ds-wizard/masmp-template) and is governed by the Apache-2.0 license. It is readily available for immediate use and can also be expanded upon in the future. It offers flexibility for modifications, such as altering SMP questions or incorporating new information into SMPs.

## GitHub Submission Service

To complete the "loop" for updating research software metadata in a GitHub repository through SMW, we developed a *submission service*. Such services in DSW allows to accept a submitted document, process it in any way, and eventually return a relevant URL back to DSW. The goal was to enable maSMP created with the previously described document template to be suggested in target GitHub repository as a Pull Request (PR).

For the service to work and be able to create PRs, we created a [`sm-wizard-bot`](https://github.com/sm-wizard-bot) account on GitHub that is the one creating forks and PRs through API (authenticated using an access token). We had to deal with various potential obstacles such as asynchronnous creation of forks via GitHub API or possibility of need of multiple forks with the same original repository name. The achieved flow with the service works as follows:

1. User generates a maSMP document in DSW.
2. User submits the (JSON-LD) document in DSW (clicks a Submit button and selects the configured service).
3. Service accepts the (JSON-LD) document and verifies the request.
4. Service extracts the GitHub repository URLs (if not present, it reports an error).
5. Service creates a fork via GitHub API (but with a name that contains also a timestamp) and then waits until the fork is being created (may take several seconds, up to minutes for larger repositories).
6. Service creates (or updates) the `metadata.json` JSON-LD file in the repository and commits the changes via GitHub API.
7. Service submits a PR to the original repository with title and message informing that it is an update submitted from SMW.
8. User gets back the URL of the PR in GitHub and it is stored next to the document in SMW.

![Selection of submission service for SMP](./figures/smp-submission.png)

This service has been successfully tested in both create and update use cases. There is no need to encode the mapping in the service as that is handled already in the document template. The only thing that is needed from the incoming JSON-LD file is presence of a triple with `schema:codeRepository` property. Then, it is tested whether the URL is actually a GitHub.com repository. It works with public repositories but can work also with private to which the `sm-wizard-bot` has access.

![GitHub Pull Request (PR) created by SMW bot](./figures/smp-github-pr.png)

As for possible future enhancements, the service can be extended to support also other than GitHub.com repositories (e.g. GitLab or BitBucket, but also GitHub Enterprise or self-hosted GitLab EE). For GitHub, it might be better to create a different mechanism for private repositories, but that would require users to enable the app for the repository; however, the question on code repository is currently following the question whether it is a public repository. Finally, a cleanup mechanism to clean forks for closed or old PRs might be needed in the future. 

![Result received from submission service to SMW](./figures/smp-submission-ok.png)

# Conclusions and Future Steps

In conclusion, the collaborative efforts undertaken during BioHackathon Europe 2023 have propelled substantial advancements in the pursuit of machine-actionable SMPs, not only within the ELIXIR framework but also extending their applicability beyond. The dedicated work accomplished during the event has resulted in a robust technical solution for seamlessly integrating SMPs with actual research software projects, marking a significant stride towards practical implementation.

Furthermore, the BioHackathon served as a catalyst for the ongoing development of SMPs. The improvements made during the event lay a solid foundation for their continuous enhancement and refinement, ensuring their relevance and effectiveness in addressing the evolving needs of the scientific and research community.

As we look to the future, the outlined roadmap emphasizes the crucial aspect of aligning SMPs with widely used metadata standards for research software projects. This strategic alignment is envisioned as a pivotal step towards fostering interoperability, standardization, and broader acceptance within the larger research ecosystem. The collaborative spirit and technical solutions generated during BioHackathon Europe 2023 set a promising trajectory for the continued evolution and impactful integration of machine-actionable SMPs, contributing significantly to the advancement of research software practices.

# Acknowledgements

This work was done during the [BioHackathon Europe](https://biohackathon-europe.org/) 2023 organised by ELIXIR in October/November 2023. We thank the organisers and fellow participants. The development and operation of DSW are supported by ELIXIR CZ research infrastructure (MEYS Grant No. LM2023055). 

# References
