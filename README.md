# What should good support preserve when AI does more of the work?

I've spent years in customer support trying to solve the right mix and balance behind "automation vs. support rep scope". In my experience, and in the support world outside, I've seen numerous decisions & sometimes mistakes being made; ones mostly to improve and optimize customer experience, but almost always to save on cost.

But with LLMs, enabling automation has suddenly become very... accessible. But to me, this is a step ahead in a [Human-Centered approach](https://hbr.org/sponsored/2026/02/keeping-customer-service-human-centered-in-an-ai-world) to using LLMs.

The projects/prototypes I have here test what that experience means as AI takes up more of the work.

## Helping people get to the next useful step

**[Copilot Lab](https://github.com/gititya/support-copilot-lab)** helps a support rep investigate a customer complaint. As the rep adds information, it asks for relevant evidence and changes its advice. The experiment follows two outcomes:

1. A fix that works.
2. A case that needs engineering.

The skill of the human rep is in determining the outcome & judgement on when to close or escalate.

**[Voice Support](https://github.com/gititya/voice-support-case-study)** explores the customer side: ask for help, get guidance inside the app, and keep control of the actions. If the help does not work, the investigation should travel with the customer to a person. The shared capabilities have been tested with a 3rd party Open Source app.

> [!NOTE]
> Both reflect how I think about human-centered AI: help the person understand and act, and leave them able to question, correct or stop it.

## Making an escalation useful

**[Handoff Gate](https://github.com/gititya/handoff-gate)** checks whether the receiving person has enough to continue. It covers AI-to-human transfers and a rep’s escalation to engineering. An unknown cause is acceptable; an unclear account of what happened is not.

**[Voice Support](https://github.com/gititya/voice-support-case-study)** uses this same gate.

## Checking the work, including the AI reviewer

**[Support Evals](https://github.com/gititya/support-evals)** reviews what happened during a support journey, not just the final answer. Did the guidance follow the customer’s progress? Was recovery confirmed? Did the receiving system acknowledge the case?

**[Quality Agency](https://github.com/gititya/support-quality-agency)** tests AI reviewers against separate support requirements. It found useful mistakes, but also let bad answers pass. That is part of the result: the reviewer needs checking too.

## Support & operations

**[Capacity Planning](https://github.com/gititya/support-capacity-planning)** asks what work remains after automation. The [article](https://substack.com/home/post/p-217364865) walks through the [calculator](https://gititya.github.io/support-capacity-planning/): fewer contacts, less human work and lower cost are three different results.

**[Signal](https://github.com/gititya/support-signal)** turns public complaints into a brief for a product investigation: what customers report, possible explanations and what to check next. The complaints give a reason to investigate; they do not establish the cause.

## Keeping the experiments that changed my mind

**[Early Prediction](https://github.com/gititya/support-early-prediction-experiment)** tried to identify a problem’s cause early in a support conversation. In these cases, the opening rarely contained enough information. That led to Copilot Lab: help the rep find out what matters next.

**[Intent Classifier](https://github.com/gititya/support-intent-classifier-experiment)** did well on familiar, structured examples and struggled with ordinary customer wording in a small set of messages. I kept the result and stopped the experiment.
