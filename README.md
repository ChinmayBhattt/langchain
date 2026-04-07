# langchain

## 1. Streaming And Batch
> Most models can stream their output content while it is being generated. By displaying output progressively, streaming significantly improves user experience, particularly for longer responses. Calling stream0 returns an iterator that yields output chunks as they are produced. You can use a loop to process each chunk in real-time:

## Batch
> Batching a collection of independent requests to a model can significantly improve performance and reduce costs, as the processing can be done in parallel:

## Tools
Models can request to call tools that perform tasks such as fetching data from a database, searching the web, or running code. Tools are pairings of:
1. A schema, including the name of the tool, a description, and/or argument definitions (often a JSON schema)
2. A function or coroutine to execute.

## Messages

>Messages are the fundamental unit of context for models in LangChain. They represent the input and output of models, carrying both the content and metadata needed to represent the state of a conversation when interacting with an LLM. 

*Messages are objects that contain:*
- Role - Identifies the message type (e.g. system, user)
- Content - Represents the actual content of the message (like text, images, audio, documents, etc.)
- Metadata - Optional fields such as response information, message IDs, and token usage.

LangChain provides a standard message type that works across all model providers, ensuring consistent behavior regardless of the model being called

### System Message
>A SystemMessage represent an initial set of instructions that primes the model's behavior. You can use a system message to set the tone, define the model's role, and establish guidelines for responses.

### Human Message
>A HumanMessage represents user input and interactions. They can contain text, images, audio, files, and any other amount of multimodal content.

### Al Message
>An AlMessage represents the output of a model invocation. They can include multimodal data, tool calls, and provider-specific metadata that you can later access.

### Tool Message
>For models that support tool calling, Al messages can contain tool calls. Tool messages are used to pass the results of a single tool execution back to the model.
