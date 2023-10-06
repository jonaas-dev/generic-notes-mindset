<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [Alien artefacts](#alien-artefacts)
  - [Help! I have an alien artefact: what can I do?](#help-i-have-an-alien-artefact-what-can-i-do)
  - [How do I avoid my team creating an alien artefact in the first place?](#how-do-i-avoid-my-team-creating-an-alien-artefact-in-the-first-place)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

# Alien artefacts

Font: <https://www.brautaset.org/posts/alien-artefacts.html>

The purpose of this blog post is to introduce the concept of alien artefacts1, a subcategory of legacy code. **I use the term to describe particularly complicated and important pieces of software written by very smart engineers that are no longer working for the company—and thus not available to support it**. The software works really well for what it was designed to do, but it is highly resistant to change.

## Help! I have an alien artefact: what can I do?

- **Understand the system**: Invest time in reviewing the code and any available documentation, and try to identify the most critical parts of the system.
- **Develop a comprehensive characterisation test suite**: This is essential to ensure that changes made to the alien artefact do not introduce bugs or unintended consequences.
- **Prioritize changes carefully**: Focus on changes that are necessary to maintain the system's functionality, rather than on non-essential cosmetic changes.

Finally, if you decide to attempt to replace your alien artefact, you may find the **strangler fig pattern** useful.

## How do I avoid my team creating an alien artefact in the first place?

- **Include junior and/or generalist engineers on the team**; avoid teams staffed entirely with specialised experts with deep domain knowledge.
- **Prioritise documentation and knowledge transfer**, and invest in ongoing development to ensure the system stays adaptable to changing business needs.
- **Use standardised coding practices** and avoid using overly esoteric languages or techniques.
