+++
date = '2026-09-24T22:04:28+02:00'
draft = false
title = 'Open Source Science meetup on generative programming'
+++

![image](https://secure.meetupstatic.com/photos/event/2/5/1/6/highres_535929494.webp?w=1080)

Yesterday I went to my first open-source event in Dublin, an Open Source Science meetup on generative computing. The presentation centered around [Mellea](https://mellea.ai/), an open-source Python library for building more structured LLM applications.

The main presentation focused on the idea of "generative programming": treating LLM calls as parts of an otherwise regular program. Mellea gives you things like typed generative functions, requirements, validation and repair loops, and constrained outputs. I like the general direction a lot. LLMs are inherently nondeterministic, which is occasionally the entire point of using one, but that becomes a pain when you want to build software around them. Having a clearer boundary around that nondeterminism makes the resulting programs easier to understand, test, and reason about as a programmer.

![image](https://media.licdn.com/dms/image/v2/D4D22AQEgor2A9fLjWg/feedshare-image-high-res/B4DaDX.o7iKMAU-/0/1790329918133?e=1792022400&v=beta&t=gOUGnEgdaB2Y44TzvL4tlc5SasbkJ1wJrklP29LV2uk)

There were also a few presentations of projects built around these ideas, which I found really interesting. I particularly liked the [Mellea skills compiler](https://github.com/generative-computing/mellea-skills-compiler), which transforms natural-language SKILLS.md files into Python scripts built with Mellea, essentially turning a natural-language description of a task into an AI call pipeline with validation and error handling. It's a great workaround for Claude's ever-changing ecosystem and also allows you to use smaller, perhaps even self-hosted models to handle complex tasks. As someone with a strong interest in compilers and programming language theory, the project really got me thinking about how you could better ensure that this sort of "compiler" preserves the semantics of the original natural-language description.

It was a very pleasant time overall. There was pizza and (non-alcoholic) drinks as well, which were much appreciated.