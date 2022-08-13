# Continuing Education

I've recently become interested in machine learning and have been studying it
in my spare time. My motivation is AI safety. A superhuman artificial
intelligence has the potential for a tremendously positive or tremendously
negative impact on an enormous number of lives. Therefore, it's crucial that if
we develop one, we do so safely. Many resources are being poured into advancing
AI's capabilities, but only a tiny amount are being spent on solving safety
problems.

I'm learning about this field in the hope that I can contribute one
day. To begin building up my knowledge, I've been taking self-directed online
courses.

## Google ML Crash Course

The first course I took was the [Machine Learning Crash
Course](https://developers.google.com/machine-learning/crash-course/) from
Google.  Before I started, I considered myself a complete novice when it came
to ML.  However, I discovered that I was already familiar with many of the
concepts, such as gradient descent and overfitting. ML may use different
jargon, but it shares a lot with traditional disciplines.

I appreciated the fact that when the course introduced a technique, they gave a
brief comparison to alternatives we'd already seen, along with some rules of
thumb about which to use when. Knowing how something works is important, but so
is knowing when to use it.

The time I found this most useful was in learning about regularization, which
is a set of techniques to reduce overfitting. The motivation for regularization
was clear to me, but I wasn't familiar with the specifics. The course explained
that L<sub>1</sub> regularization, which aims to minimize the absolute values
of a model's weights, can drive some weights to zero, which helps to improve
computational performance when there are a large number of features (inputs).
L<sub>2</sub> regularization, which aims to minimize the square of the weights,
will tend to keep weights from getting too large. But it typically doesn't
drive them to exactly 0 because its effect on the gradient diminishes as the
weights get smaller.  Dropout regularization, which removes random nodes from
the network at each iteration, is similar to averaging over an ensemble of
smaller networks.

## fast.ai Practical Deep Learning for Coders

The creators of [fast.ai](https://www.fast.ai/), which supplements the popular
PyTorch library, offer their own [introductory machine learning
course](https://course.fast.ai/).  While I was in the middle of the course,
they released an updated 2022 version.  My comments here are about the earlier
2020 version, so I apologize if any of them are out of date.

For me, one key takeaway from the course was the importance of picking a good
baseline to compare a ML model to. An accuracy of 75% may sound good, but if
always picking the average would give an accuracy of 80%, it's clear the ML
model isn't performing well. However, a trivial baseline isn't always the best
choice. Sometimes it's better to use a heuristic that is much simpler than the
ML model but still captures some of the underlying relationship. Ultimately,
just as one would make a best effort on developing a ML model, one should make
a best effort on a non-ML baseline.

The course devoted one of its eight lectures entirely to ethics discussions, a
substantial amount for an introductory course like this. The lecturer for that
class, [Rachel Thomas](https://rachel.fast.ai/), shared many examples of the
negative effects ML and AI can have, with some questions to keep in mind to
help catch potential problems early. While there usually aren't clear solutions
to these sorts of ethical issues, at least being aware of how many ways things
can go wrong reinforces the point that everyone in the field should feel
responsible for thinking about and working on them.

Dr. Thomas made the explicit point to focus on ethical issues of the present
that are affecting people now and not on issues that future generations may
face. Six months ago, I would have whole-heartedly agreed. Why spend time on
hypothetical future problems when we have concrete ones in front of us today?

However, I've recently changed my mind about this. Some problems may not be
possible to solve once they are realized. For instance, it might be impossible
to switch off a superhuman AI if it starts acting in undesirable ways.
Therefore some problems need to be prevented altogether and not addressed
reactively.

It's also important to keep in mind that the future will likely have many more
people than the present, not just at any moment but especially in total. And
their concerns are particularly neglected today: they can't vote, protest or
advocate for themselves. To me, that's all the more reasons to prioritize the
issues of the future, like figuring out how to create an AI that aligns with
our values, now.
