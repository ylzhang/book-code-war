# Chapter 11: The Murdered Classical Intermediary

November 30, 2022. San Francisco.

Sam Altman pressed Enter, and ChatGPT officially went live.

In OpenAI's office, engineers nervously stared at the monitoring screens. Server load spiked, and the speed of user influx exceeded everyone's expectations.

Altman wore a gray hoodie—the standard uniform of Silicon Valley entrepreneurs. His eyes were focused and calm, as if all of this was expected. As a former president of Y Combinator, he had seen the ups and downs of countless startups. But this time, he knew something was different.

Within five days, ChatGPT surpassed 1 million users. Within two months, 100 million users. This was the fastest-growing consumer application in human history.

Search was obsolete.

---

What is ChatGPT?

It is a chatbot. You input a question, it provides an answer. It can be a writing assistant, a programming tutor, a translation tool, a psychological counselor... It seems to know everything and can do everything.

But what is the essence of ChatGPT?

It is a large language model. It has read nearly all the text on the internet and learned the patterns of language. When you input a question, it predicts the most likely response.

This prediction process is called "generation."

The success of ChatGPT marks the official arrival of the AI era. It also marks the birth of a new form of network: the intent-driven network.

In the traditional internet, you need to search, browse, and click to find the information you want. In the intent-driven network, you simply state your intent, and AI completes everything for you.

This means that classical intermediaries are being murdered.

---

How do large language models work?

In 2017, Google researchers published a paper titled "Attention Is All You Need." This paper proposed the Transformer architecture, which became the foundation of large language models.

The core of Transformer is the "attention mechanism."

In traditional recurrent neural networks, information is passed sequentially. The model processes the first word, then passes the result to the next word, and so on. The problem with this approach is that long-distance dependencies are difficult to capture. The relationship between the first word and the last word is lost in the transmission process.

Transformer adopts the "self-attention" mechanism. Each word can directly "attend" to all other words, calculating their relevance. This way, no matter how far apart two words are, the model can capture the relationship between them.

Transformer also introduces "positional encoding," allowing the model to know the position of each word in the sentence. This way, the model can not only understand the meaning of words but also their order.

---

The training of large language models is divided into two stages: pre-training and fine-tuning.

Pre-training: The model reads massive amounts of text and learns the patterns of language. The goal of this stage is to make the model "learn to speak." The amount of data for pre-training is usually several hundred GB to several TB, and the training cost is several million to tens of millions of dollars.

Fine-tuning: The model is trained on specific tasks, learning how to answer questions and follow instructions. The goal of this stage is to make the model "learn to obey."

OpenAI's GPT series models are trained using an "autoregressive" approach. The model predicts the probability distribution of the next word, then compares it with the actual next word, calculates the loss, and updates the parameters.

GPT-3 has 175 billion parameters, and the training data is 45TB of text. The training cost is estimated at $12 million.

GPT-4's parameter count has not been disclosed, but it is estimated to exceed 1 trillion. The training cost is estimated to exceed $100 million.

---

The success of ChatGPT is not only due to the large model but also because of good training methods.

OpenAI adopted the method of "Reinforcement Learning from Human Feedback" (RLHF).

The process is as follows:

First, human annotators write questions and answers, and the model learns how to answer questions.

Then, human annotators rank multiple answers from the model, and the model learns what kind of answers are better.

Finally, the model generates answers, the reward model gives scores, and the model adjusts parameters based on the scores.

This taught the model "alignment": generating answers that conform to human values and avoiding harmful content.

But this also brought problems. It made the model "safer" but also "boring." The model tends to give neutral, vague answers, avoiding controversial viewpoints.

---

Inference of large language models requires massive computational resources.

GPT-3's inference requires dozens of GPUs. Every time a user asks a question, the model needs to perform billions of floating-point operations to generate an answer.

This brings two problems:

Cost: The cost of each inference is a few cents to a few dimes. If there are hundreds of millions of requests per day, the cost is enormous.

Latency: Generating an answer takes several seconds. Users may not have the patience to wait.

Solutions include model compression, edge inference, and caching. By 2023, the inference cost of large language models has dropped significantly. OpenAI's API price dropped from the initial $0.06 per thousand tokens to $0.002 per thousand tokens.

---

The emergence of ChatGPT threatened Google's search business.

In 2022, Aravind Srinivas founded Perplexity AI.

Perplexity is an "answer engine." Users input questions; Perplexity doesn't return a bunch of links but directly gives answers with cited sources.

Perplexity's success proves that users prefer direct answers rather than searching through links themselves.

Google was forced to respond. In 2023, Google launched Bard, then renamed it Gemini. But Gemini's performance was not as good as ChatGPT, and Google's stock price was affected.

Microsoft saw the opportunity. It invested $10 billion in OpenAI and integrated ChatGPT into Bing search. Bing's market share began to rise.

The search war reignited.

---

The emergence of large language models also threatened content platforms.

If AI can generate articles, why do users need to read articles written by humans?

If AI can generate videos, why do users need to watch videos shot by humans?

If AI can generate music, why do users need to listen to music composed by humans?

Content platforms face existential crises.

But content platforms are also using AI. TikTok uses AI to recommend content; YouTube uses AI to generate subtitles; Netflix uses AI to recommend movies.

AI is not replacing content platforms but changing the way content is produced and distributed.

---

DeepSeek is a Chinese AI company. In 2024, it released DeepSeek-V3, shocking the global AI community.

DeepSeek-V3's performance is comparable to GPT-4o, but the training cost is only a few million dollars—one-tenth of GPT-4o.

DeepSeek's success proves that Chinese companies can also develop world-class large language models.

More importantly, DeepSeek-V3 is open source. Anyone can download, use, and modify this model. This is a challenge to closed-source models and a push for AI democratization.

DeepSeek's founder, Liang Wenfeng, believes that computing efficiency is the key to AI development. Under the background of computing power blockade, Chinese companies cannot obtain the most advanced GPUs and can only make up for it through efficiency.

"Americans have their advantages, and we also have our advantages," Liang Wenfeng said. "We have the world's largest manufacturing industry, the most complete supply chain, and the richest application scenarios. These advantages can be transformed into AI advantages."

---

In the spring of 2024, I first used ChatGPT.

I asked it a programming question: how to implement a linked list in Python. It gave a clear answer with code examples.

Then I asked it to explain the principles of blockchain. It gave a detailed explanation with diagrams.

Finally, I asked it to write a short story. It wrote a story about AI awakening.

That feeling was like having an omniscient teacher, patient, professional, never tired.

But I also noticed its limitations. It sometimes "hallucinates," generating false information. It sometimes gives "safe" but useless answers. It doesn't really "understand" but just predicts the next word.

AI is powerful, but AI is not omnipotent.

---

**Epilogue: 2026**

GPT-5 is released.

It is no longer just a chatbot but an "agent." It can browse the web, operate software, and execute tasks. You tell it "help me book a flight to New York," and it opens the airline website, queries flights, chooses the most suitable one, and completes the booking.

You don't need to open any APP. You just need to talk to GPT-5.

Is the APP dying?

The destiny of code depends on the people holding the keyboard.

And the next chapter of the story has just begun.