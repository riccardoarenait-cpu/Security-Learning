# Prompt engineering

LLMs break down your prompt into singular words or part of a word, then it turns them into tokens consisting of numbers, the machine uses those numbers to predict the next words

Nondeterminism : two identical inputs into a LLM will provide different outputs

Temperature : determines the randomness of the model

System prompts : developer defined instructions that set the assistant's rules

the instruction hierarchy isn't solid, a model treats every instruction as text no matter where it comes from, it only learns to distinguish system promts during training, meaning there isn't a 0% change a user prompt can bypass them

Adding shots to a prompt : providing examples to define expectations 


















