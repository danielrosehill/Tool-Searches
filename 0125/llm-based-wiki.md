# LLM Based Wiki & KM System

*06-Jan-25*

What happens when a "data hoarder" discovers and becomes fascinated with large language models?  I could tell you because I am that person and 2024 was a year of exploring these tools for me!

When I had the pennydrop moment, like many, that large language models were vastly more useful than just for generating funny text and images, my thoughts turned quickly to *"well, how do we store the content that they generate?"*

## Why does output storage get such little attention?

Firstly, let me share a few thoughts about why I think that output storage is going to emerge as a huge focus in large language model centric workflows of the present and near future:

But first, let me outline the scope:

I didn't and don't see the need to store every little line of text that large language models generate. As is well known, much of it is often not that useful or requires careful prompting to yield an output that is actually helpful for solving or advancing a business use case or a personal needs. There is no point in storing outputs that are not useful or which contain hallucinations. 

However, when we finally get to the point at which we have gotten some good quality information from a model that could be useful (or already is!), there becomes a moment where it would be useful to have a reliable and seamless system for storing those outputs into some kind of information organization system, such as a Google Drive or a wiki. After all, we've paid to get this data from the large language model! Shouldn't we put it somewhere? 

When you think about it, it's kind of strange that we put so much effort into prompt management and so little into what to do with outputs. The whole point of versioning and improving prompts is to generate better outputs from models. So my contention remains that we should invest some energy in finding elegant ways to anage outputs!

## Why not store outputs in LLM frontends?

As what I intended to be an outline of my spec search has turned into more of a blog, I'll address a common point of contention, or at least what I imagine it to be

 Can't you store your outputs in ChatGPT or Perplexity? Increasingly, yes, but this comes with a few big deficiencies:

 1) Storing potentially valuable AI outputs here is trusting one vendor with managing all of your business data. Most companies continue to see value in copying and amassing data derived from using cloud tools.   
 2) If the present of the AI landscape is anything to indicate why, future trends will look like, businesses and consumers are increasingly using a plurality of tools and front ends to interface with large language models. Given this kind of use, it makes sense to decouple the storage of LLM generations from the front ends used for interaction, particularly given the fact that outputs from one model can be provided as inputs or context to another - for example by deploying them into a vector database

## My vision for an ideal LLM frontend

So here's the type of large language model frontend which I would love to have at my disposal, and which I'd happily pay to access should anyone make one. 

In the absence of such innovation, I might get around to eventually trying to make this myself, or more probably I'll try to nudge those who are already ahead of the game in developing front ends to consider integrating this as a feature

The features would be:

1) The existing crop of features that are becoming increasingly standardized in LLM frontends (LibreChat, Big-AGI, etc). Think the interface for actually chatting with the models, a settings page for managing API keys and the models you're using; an agents page for setting up system prompts attached to specific models. 
 
 2) What I would regard as the missing component: functionalities for output routing. Here I'd envision the user being able to configure connections to all the classic places where people and enterprises like to store data. Starting with consumer level storages such as Google Drive and working up to more enterprise ready storages like S3 and B-2 buckets all the way through to data warehouses. Given how tightly LLMs and RAG are interrelated It would make abundant sense to provide connectivity to external vector databases also. 

With these configurations in place, users would be able to engage at scale with different models while knowing that their outputs were being reliably and robustly archived into business storage systems, which they managed and could in turn back up.

User settings that could be provided might include giving users the ability to automatically store all outputs in their target storage, or selectively store those which they have to manually configure. 

Better still might be the ability for users to route the data in multiple ways! At the click of a button, a conversation might be passed into a workflow that writes it into both vector storage and let's say a Postgres (for this use case, imagine a conversation that's identified as having value both as contextual data and as business data.). 

## Use-cases for output storage

Beyond the simple use case of information retrieval and having the information accessible, there are some additional use cases that could be opened up if outputs as well as prompts were stored, ideally together and in a related data store:

- Secondary AI systems: As use of AI system scales, it becomes challenging for users to keep track of all the generations that have previously been done. But this is a sensible strategy to use as it avoids having to run repetitive prompts to yield the same information. Having a robust and well indexed output store can mean that there is a treasure trove of  existing AI generations that any user can use.

- Trend Analysis: As the human authored element in AI workflows (at least usually) prompts capture some interesting data about how our interests and priorities evolve over time. Natural language mining could be brought on top of a inventory of prompts and outputs in order to try to generate some insights about how the user's interests and prioritize have moved over time, and whether any insights can be derived from this data. With powerful vector stories easily affordable, these type of use cases could be easily achieved. Reliable output storage would be a great first step towards enabling them.