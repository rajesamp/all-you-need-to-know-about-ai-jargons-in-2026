Agentic AI — Jargon Glossary 

MODELS & FUNDAMENTALS

LLM (Large Language Model)
What it is: A neural network trained on billions of text documents to predict the most likely next word, over and over.
Remember it: It's not a search engine with a database of facts — it's a next-word prediction machine that got so good at predicting, it learned to reason. Think autocomplete that went to college.

Token
What it is: The smallest unit of text an LLM processes — roughly ¾ of an average word. "unhappy" = 2 tokens: "un" + "happy".
Remember it: Tokens are like coins in an arcade — the LLM has a limited number it can hold at once (context window), and every word you type spends some of them.

Context Window
What it is: The total amount of text (in tokens) an LLM can "see" at one time — everything in the conversation, the system prompt, documents, everything.
Remember it: It's the LLM's RAM — not its hard drive. When the window fills up, old stuff falls off the edge and is forgotten.

Parameters
What it is: The billions of numerical weights inside the model, adjusted during training, that determine how it responds to any input.
Remember it: Parameters are the model's personality baked in from training — 70 billion tiny knobs, all tuned at once, that define what "llama-3.3-70b" knows and thinks.

Temperature
What it is: A setting (0 to 1+) that controls how random or creative the LLM's outputs are. 0 = always picks the most likely word. 1+ = rolls the dice more.
Remember it: Temperature = how much coffee the model had. temperature=0 is a sleepy accountant — always picks the safe answer. temperature=1 is a brainstorming artist — surprising every time.

Transformer Architecture
What it is: The neural network design used by all modern LLMs. It processes all tokens in parallel using a mechanism called attention to understand relationships between words.
Remember it: Before transformers, models read left-to-right like a person reading slowly. Transformers read the whole sentence at once and ask "which words should I pay attention to?" — that's why they're so fast and powerful.

PROMPT ENGINEERING
Prompt Engineering
What it is: The practice of carefully crafting your input — instructions, examples, context — to get the best possible output from an LLM.
Remember it: You're not programming a computer, you're briefing a very smart intern. The more specific and structured your brief, the better the output.

System Prompt
What it is: An instruction you give to the LLM at the start of a session that sets its role, behavior, tone, and rules — before any user interaction.
Remember it: The system prompt is the job description. You're telling the LLM "you are a conservative financial advisor" before any customer walks in the door.

User Prompt
What it is: The actual question or task the user sends in each turn of the conversation.
Remember it: If the system prompt is the job description, the user prompt is each individual customer request. New request every time, same role always.

Instruction Structuring
What it is: Breaking your prompt into four explicit parts: Role (who the LLM is), Task (what to do), Context (background info), and Output Format (how to deliver the answer).
Remember it: Think of it like a work order form — if you hand someone a vague sticky note they'll do the wrong thing. Fill in all four fields and they'll nail it every time.

Zero-Shot Prompting
What it is: Asking the LLM to do a task with no examples — just the instruction itself, relying entirely on what it learned during training.
Remember it: Throwing someone into the deep end on Day 1. No examples, just "figure it out." Works well for common tasks but fails for niche or unusual formats.

Few-Shot Prompting
What it is: Providing 1–5 examples of your desired input-output format inside the prompt before asking the model to do the real task.
Remember it: Show don't tell. You show the model three examples of what a good answer looks like, then it pattern-matches for you. Like showing a new hire sample reports before asking them to write one.

Chain-of-Thought (CoT)
What it is: Adding "think step by step" (or showing reasoning steps in examples) to force the LLM to work through a problem incrementally instead of jumping to an answer.
Remember it: Without CoT, the LLM guesses the answer fast (and often wrong on hard problems). With CoT, it shows its work — like the difference between a student who just circles an answer vs one who writes out all the math. CoT went from 18% → 57% solve rate on hard math.

Negative Prompting
What it is: Explicitly telling the LLM what NOT to do, include, or say in the response.
Remember it: "Don't add disclaimers. Don't use bullet points. Don't start with 'Certainly!'" — this is negative prompting. You're trimming the output by eliminating unwanted habits.

Step Back Prompting
What it is: Before answering, ask the LLM to reframe the question at a higher/broader level first, then use that reframed version to answer.
Remember it: Instead of asking "what medicine treats condition X?" step back and ask "what is the mechanism of condition X?" first — the broader understanding leads to a better answer.

Prompt Chaining
What it is: A pipeline where the output of one LLM call becomes the input of the next — like an assembly line where each station does one job.
Remember it: Summarize → Classify Sentiment → Generate Suggestion. Each step does one thing well, and passes the baton. No single prompt tries to do everything at once.

Iterative Refinement
What it is: Treating prompting as an experiment — write, test, observe the failure, adjust, repeat.
Remember it: Your first prompt is never your best prompt. Think of it like seasoning food — you taste, adjust, taste again until it's right.

RAG (RETRIEVAL AUGMENTED GENERATION)
RAG
What it is: A technique that retrieves relevant documents from a knowledge base and stuffs them into the LLM's prompt before it answers — so the model can answer from real, current data instead of just training memory.
Remember it: RAG is giving the LLM an open-book exam. Without it, the LLM has to rely on what it memorized (closed-book). With it, you hand it the relevant textbook pages right before the question.

Chunking
What it is: Breaking large documents into smaller pieces (chunks) so they fit inside the LLM's context window and can be retrieved individually.
Remember it: You can't feed an entire encyclopedia into the LLM — so you cut it into index cards. Each index card is a chunk. The retriever finds the right index cards for each question.

Fixed-Size Chunking
What it is: Splitting a document every N tokens/characters regardless of where sentences or paragraphs end.
Remember it: Like cutting a loaf of bread with a ruler — every slice is exactly the same width whether it hits mid-crust or mid-slice. Fast, simple, but occasionally messy.

Semantic Chunking
What it is: Splitting the document based on meaning shifts — a new chunk starts only when the topic changes significantly (measured by a drop in cosine similarity between sentences).
Remember it: Like a smart editor who knows "this paragraph changed subject" and starts a new section. More work, but each chunk is one coherent idea.

Chunk Overlap
What it is: Letting consecutive chunks share some tokens at their boundaries so important sentences aren't split across two separate chunks.
Remember it: Like having the last line of page 1 also appear at the top of page 2 — ensures nothing important gets orphaned at the edge of a chunk.

Embedding
What it is: A mathematical representation of text as a dense list of numbers (a vector) where similar meanings produce similar vectors.
Remember it: Every word, sentence, or chunk gets converted into GPS coordinates in meaning-space. "Dog" and "puppy" end up close. "Dog" and "mortgage" end up far apart.

Embedding Model
What it is: The model that converts text into embeddings — like all-MiniLM-L6-v2 (fast, 384 dimensions) or OpenAI's text-embedding-3.
Remember it: The embedding model is the translator between human language and math. You pass in text, it returns a list of ~384 numbers that encode what that text means.

Vector
What it is: An ordered list of numbers (e.g., [0.3, 0.9, -0.1, 0.5 ...]) that represents the meaning of a piece of text in multi-dimensional space.
Remember it: Think of it as the text's "fingerprint" — unique, numerical, and allows computers to calculate how similar two pieces of text are using math instead of words.

Vector Space
What it is: The high-dimensional mathematical space where all embeddings live. Similar meanings cluster together, opposites sit far apart.
Remember it: Imagine a giant invisible map where every word and sentence has a location. "King" and "Queen" are neighbors. "Paris - France + Italy = Rome" is actual math you can do on this map.

Cosine Similarity
What it is: A formula that calculates the angle between two vectors. The smaller the angle (closer to 0°), the more similar the meaning. Score ranges from -1 to 1 (1 = identical).
Remember it: Two arrows pointing in the same direction = same meaning. Two arrows pointing opposite directions = opposite meaning. The formula measures the angle between them — not how long they are, just which way they point.

Vector Database
What it is: A database specifically built to store embeddings and find the nearest neighbors to a query vector extremely fast (e.g., Pinecone, Chroma, Qdrant).
Remember it: A regular database asks "find rows where name = 'Alice'." A vector database asks "find the 5 chunks whose meaning is closest to this query." It's a meaning search engine.

Retriever
What it is: The component in RAG that takes the user's query, converts it to an embedding, and finds the most semantically similar chunks from the vector database.
Remember it: The librarian in RAG. You ask a question, the librarian runs to the stacks and comes back with the 3 most relevant books. The LLM then reads them and answers.

Top-K
What it is: A parameter that tells the retriever how many chunks to return (e.g., K=3 means return the 3 most similar chunks).
Remember it: Like Google's "I'm feeling lucky" vs showing you 10 results. Top-K=3 means "give me the three best hits and I'll work with those."

Context Engineering / Augmentation
What it is: The step in RAG where you take the retrieved chunks and the original question and assemble them into a final, well-structured prompt for the LLM.
Remember it: The retriever found the index cards. Context engineering is arranging those cards neatly on the desk before the LLM sits down to read them.

Groundedness / Faithfulness
What it is: A metric measuring whether every claim in the LLM's answer can be traced back to something explicitly in the retrieved context — nothing invented.
Remember it: Like a research paper — every statement should have a citation. If the LLM says something that's NOT in the context, that's a faithfulness failure (hallucination).

Hallucination
What it is: When an LLM confidently states something false or fabricated — presenting invented information as fact.
Remember it: The LLM is a next-word predictor, not a fact-checker. When it doesn't know, it still predicts confidently — and what it predicts can be completely wrong. It "hallucinates" a plausible-sounding answer.

Ground Truth / Golden Response
What it is: A human-written correct answer used as the benchmark to evaluate whether the LLM's answer is accurate.
Remember it: The answer key at the back of the textbook. You score the LLM's answer by comparing it against the answer key. No key = no objective way to know if the LLM passed.

RETRIEVAL & RERANKING
BM25
What it is: A classic keyword-based ranking algorithm that scores documents by how often the query words appear in them, weighted by how rare those words are across all documents.
Remember it: BM25 is the old librarian who only looks at word counts — "this document says 'COVID' 8 times, must be relevant." It's fast and has no understanding of meaning. If you ask "car" it won't find documents that say "automobile."

TF-IDF
What it is: Term Frequency × Inverse Document Frequency — scores a word by how often it appears in this doc (TF) divided by how common it is across all docs (IDF). Rare words that appear here score highest.
Remember it: "The" appears everywhere → IDF makes it worthless. "Mitochondria" appears rarely → IDF makes it precious. TF-IDF rewards specific, rare words that actually define a document's topic.

Bi-Encoder
What it is: An embedding approach where the query and each document are encoded separately into vectors, then compared by cosine similarity at search time.
Remember it: Two separate translators — one encodes the query, another encodes each document. They never talk to each other, just compare their translations. Fast because you pre-encode all docs, but approximate because query and doc never directly interact.

Cross-Encoder / Reranker
What it is: A model that takes the query AND one document together as a single input and outputs a single relevance score — they interact directly inside the model.
Remember it: The cross-encoder is a judge who reads both the question AND the document side-by-side before scoring. Much smarter than comparing separate translations, but you can't pre-encode — so it's slow.

Two-Stage Retrieval
What it is: First use a fast Bi-Encoder + BM25 to get hundreds of candidates, then use a slow Cross-Encoder to rerank only those top candidates into a final precise list.
Remember it: Stage 1 is a wide fishing net (fast, catches a lot). Stage 2 is a chef picking through the catch and throwing back the bad fish (slow, precise). You never run the chef on the whole ocean.

HyDE (Hypothetical Document Embeddings)
What it is: Before searching, ask the LLM to write a fake ideal answer to the query, then use that fake answer as the search query instead of the raw user question.
Remember it: Instead of searching with "what causes inflation?" (a question), you generate "Inflation is caused by..." (an answer), and search with that. Answers are closer to documents in vector space than questions are — so you find much better matches.

MAP (Mean Average Precision)
What it is: A single number summarizing retrieval quality across multiple queries — it rewards systems that return relevant documents early (high in the ranked list).
Remember it: MAP is your retriever's report card GPA. It asks: "Across all your test queries, how often were the right documents near the top of your results?" High MAP = your retriever ranks relevant docs first, every time.

Precision@K
What it is: Of the top-K results returned, what fraction were actually relevant?
Remember it: You asked for 3 results. 2 of the 3 were relevant. Precision@3 = 2/3 = 67%. It measures "how accurate is the top of my list?"

Recall@K
What it is: Of all the relevant documents that exist in the database, what fraction did you find in your top-K results?
Remember it: If there are 10 relevant docs total and you retrieved 4 of them in your top-K, Recall = 4/10 = 40%. It measures "how many did I miss?" High recall = nothing left behind.

Cache Hit Rate
What it is: The percentage of retrieval calls where the result was already stored from a previous identical query, so no new computation was needed.
Remember it: Like browser cache — the first time you visit Google, it loads slow. After that, cached. Cache Hit Rate measures how often your RAG system is "already done" before it even starts.

TOOL CALLING & AGENTS
Tool
What it is: A Python function exposed to the LLM so it can request to run it — giving the LLM the ability to do things it can't do with text alone (math, live database lookups, web searches, etc.).
Remember it: An LLM without tools is a genius locked in a room with no phone. Tools are the phone. Give it a calculator tool and it never does arithmetic wrong again.

@tool Decorator
What it is: A LangChain decorator that wraps a Python function and packages its name, docstring, and parameters into a format the LLM can understand and request.
Remember it: @tool is how you put a Python function on the LLM's "menu." The LLM reads the docstring like a menu description and decides if it wants to "order" that function.

bind_tools()
What it is: A LangChain method that attaches a list of tools to an LLM instance, so the LLM knows those tools exist and can request to call them.
Remember it: bind_tools() hands the LLM the menu before the conversation starts. Without it, the LLM doesn't know the tools exist. With it, it can order any item on the list.

tool_calls
What it is: A field on the LLM's response — instead of returning plain text, the LLM returns a list of tools it wants to call with the arguments it wants to pass.
Remember it: When the LLM can't answer directly, it places an order — "I need square_root(144) before I can answer." The tool_calls field IS that order ticket.

ToolMessage
What it is: A special LangChain message type used to send the result of a tool call back to the LLM, so it can use that result in its next response.
Remember it: The kitchen (your Python code) ran the tool and got a result. ToolMessage is how the waiter brings the food back to the LLM's table so it can finish cooking the final answer.

tool_map
What it is: A Python dictionary mapping tool names (strings) to actual tool functions — used to look up and execute the right function when the LLM requests a tool by name.
Remember it: The LLM says "call calculate_reorder_quantity." Your code looks up tool_map["calculate_reorder_quantity"] and runs it. It's the phone directory between the LLM's request and your actual code.

Agent Loop
What it is: The repeating cycle an agent runs: call the LLM → if it requests tools, run them and feed results back → repeat until the LLM gives a final answer with no more tool calls.
Remember it: Think → Act → Observe → Think → Act → Observe → Done. The LLM keeps looping until it decides "I have everything I need, here's the final answer." The while True loop in code IS the agent.

Docstring
What it is: The """description""" comment inside a Python function that explains what it does, what its parameters mean, and what it returns.
Remember it: The LLM never reads your function's code — it only reads the docstring. A vague docstring = wrong tool selection. A precise docstring = the LLM uses it exactly right. It's the most important comment you'll ever write.

StrOutputParser
What it is: A LangChain component at the end of a chain that strips away the AIMessage wrapper and returns just the raw text string.
Remember it: The LLM returns an object with a .content field full of metadata. StrOutputParser tears off the packaging and hands you just the text. It's the unboxer at the end of the assembly line.

RunnableLambda
What it is: A wrapper that converts any plain Python function into a LangChain-compatible "Runnable" — so it can live between two steps in a | pipe chain.
Remember it: The LangChain pipe | only connects Runnables. Your custom function isn't a Runnable. RunnableLambda(my_func) is the adapter plug that makes your function compatible with the pipe system.

LCEL (LangChain Expression Language)
What it is: A syntax using the | (pipe) operator to chain LangChain components together — prompt | llm | parser — so data flows through each step automatically.
Remember it: It's the Unix pipe for LLMs. cat file | grep word | sort — same idea. Each | passes the output of the left into the input of the right. prompt | llm | parser = format → generate → clean.

MCP (MODEL CONTEXT PROTOCOL)
MCP
What it is: An open standard (created by Anthropic) that defines how AI agents communicate with external tool servers — a universal plug-and-play interface for AI tools.
Remember it: Before USB-C, every phone had a different charger. MCP is USB-C for AI — any agent speaks MCP, any tool server speaks MCP, and they just work together without custom glue code.

MCP Host
What it is: The AI agent application (like Claude Desktop, your chatbot, etc.) that wants to use tools and contains the MCP Client.
Remember it: The host is the laptop — the device that needs to connect to something external. It contains the client software that initiates the connection.

MCP Server
What it is: The server that exposes tools (functions) over the MCP protocol — it's the thing the agent connects to in order to call tools.
Remember it: The MCP Server is the USB hub on the other end. It has tools plugged into it (weather API, file system, calendar), and the agent plugs in to use any of them.

MCP Client
What it is: The software component inside the host that speaks the MCP protocol and communicates with the MCP Server via JSON-RPC messages.
Remember it: The MCP Client is the USB-C port on the laptop — the physical interface that knows how to speak the standard protocol to connect to any compatible device.

JSON-RPC
What it is: A lightweight protocol for making remote function calls using JSON-formatted messages — the language MCP uses to send tool requests and receive results over HTTP.
Remember it: JSON-RPC is the language spoken between host and server. It's like texting orders to the kitchen: {"method": "get_weather", "params": {"city": "Dallas"}} — structured, readable, and standardized.

Initialize Handshake
What it is: The mandatory 3-step exchange (request → result → "initialized" notification) that happens at the start of every MCP session before any tools can be called.
Remember it: Like a work badge scan when you enter the office. You have to complete the handshake before any doors open. Skip it and nothing works.

Capabilities Negotiation
What it is: During the handshake, the client and server tell each other which optional features they support. Unknown capabilities are ignored — allowing each side to evolve independently.
Remember it: Two people meeting for the first time and saying "I speak English, Spanish, and Python." The other person says "I speak English and Java." They agree to use English. Neither breaks if the other knows something extra.

FastMCP
What it is: A Python library that makes building MCP servers easy — you just add @mcp.tool() decorators to your functions and it handles all the protocol machinery automatically.
Remember it: FastMCP is to MCP what Flask is to HTTP. Without
