+++
date = '2026-11-22T12:00:00+00:00'
draft = false
title = 'PyCon Ireland 2026'
tags = ['IT']
description = ""
image = "https://assets.galfajon.dev/pictures/pycon/robot_talk.jpg"
imageAlt = "Two speakers beside a projected Counter-Strike 2 demo at PyCon Ireland"
+++

Yesterday I attended [PyCon Ireland](https://2026.pycon.ie/), a cosy Python-focused conference in Dublin city centre. It was a really pleasant and well-organised experience with a casual and welcoming atmosphere.

I started the day off by attending a few talks. These focused on AI and machine learning, touching on things like training robots to play video games, orchestrating agents and creating economic prediction models. The highlight was a [talk][robots] by [Jonas Mayer][jonas] and [Thomas Endres][thomas] of [TNG Technology Consulting](https://www.tngtech.com/) about getting an AI to simulate inputs and successfully play Counter-Strike 2. It was both very educational and extremely funny.

I dedicated the second portion of the day to a [quantum computing workshop][quantum] with [Pablo Suárez Vieites][pablo] and [Karthik Krishnakumar][karthik] of the [Irish Centre for High-End Computing](https://www.ichec.ie/), where we experimented with the [Qiskit](https://quantum.cloud.ibm.com/docs/en/guides) library for quantum circuits. We had a short introduction to the algebra behind qubits and familiarised ourselves with the gates these circuits use, how to generate superpositions and how basis states work. The workshop concluded with us implementing the Deutsch–Jozsa algorithm, which can determine whether a function is constant or balanced, given the promise that it is one or the other.

{{< figure src="https://assets.galfajon.dev/pictures/pycon/quantum.jpg" alt="ICHEC workshop slide on my laptop showing qubit measurement probabilities alongside Schrödinger’s cat" width="640" >}}

I ended the day with a [workshop][tau-workshop] by [Alejandro AO](https://alejandro-ao.com/) of [Hugging Face](https://huggingface.co/), explaining the inner workings of agents and introducing [Tau](https://twotimespi.dev/), an easy-to-read agent codebase. His presentation was very well designed, and he made a great effort to connect with the audience. I also tried the agent with a locally hosted Ollama model. It was able to generate a little game for me while allowing me to view its thinking output and tool calls, providing a great demonstration of how agents like Codex or Claude Code work on a small scale.

He also guided us through the way these agents store and reference conversations and compact their context. He gave us some advice on making the most of an agent’s cache and using context to improve the quality of its work. He even showed us a few examples of agents he personally trained for his everyday tasks. I came away wanting to read more of the [Hugging Face research articles](https://huggingface.co/blog) and the [original ReAct paper](https://arxiv.org/abs/2210.03629) on how language models combine reasoning with action.

{{< figure src="https://assets.galfajon.dev/pictures/pycon/bathroom.jpg" alt="Mirror selfie with my PyCon Ireland badge and a peace sign" width="640" >}}

As someone who has spent the last half a decade focusing primarily on web application development, I find these conferences always provide me with a great sampler of everything else that is out there in the field. I left the event with a long reading list, some stickers and plenty of motivation to continue pursuing the discipline we all love.

- [Full conference programme](https://2026.pycon.ie/schedule/)
- [All speakers and affiliations](https://2026.pycon.ie/speakers/)

[robots]: https://2026.pycon.ie/schedule/#session-1306952

[jonas]: https://2026.pycon.ie/speakers/#c6d5c0cd-df49-4938-9dbe-cd74002f73f1

[thomas]: https://2026.pycon.ie/speakers/#dd1835e4-cf2e-4122-b9d0-59f59914b5ee

[quantum]: https://2026.pycon.ie/schedule/#session-1319840

[pablo]: https://2026.pycon.ie/speakers/#77c50432-5563-459f-a7eb-2fa400a196f1

[karthik]: https://2026.pycon.ie/speakers/#0c9d03b5-4cca-4aed-b286-df74d8d0c84f

[tau-workshop]: https://2026.pycon.ie/schedule/#session-1373609
