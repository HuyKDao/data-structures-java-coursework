# NGordnet: Word Trends & WordNet

**Course:** CS 61B, Data Structures (UC Berkeley, Fall 2022), Projects 2A and 2B

**Goal:** build the back end of a small web tool, similar to Google Ngram Viewer, that shows how often words appear in books over time and explores how words relate to each other.

## Data
- **Google Books Ngram** counts (how often each word appears each year).
- **WordNet**, a lexical database that groups words into synonym sets ("synsets") linked by "is a kind of" relationships (hyponyms).

## What I did
**Part A: word trends (time series)**
- Implemented a `TimeSeries` class on top of Java's `TreeMap` (years in sorted order) with element-wise addition and division across years.
- Built an `NGramMap` that loads word and total-count files into a `HashMap` of time series and answers queries for a word's raw counts, its relative frequency, and the summed frequency of a group of words over any year range.
- Wired these into query handlers that return text results and plots to the web front end.

**Part B: WordNet hyponyms (graphs)**
- Modeled WordNet as a **directed graph** of synsets and built a `HashMap` index from each word to every synset containing it, since one word can have several meanings.
- Answered "find all hyponyms" queries with a recursive **depth-first traversal** that collects every word below a synset, deduplicated with a `HashSet` and sorted alphabetically.
- Supported **multi-word queries** by intersecting each word's hyponym set.
- Added a **top-k popularity filter**: for a given year range, it sums each candidate's Ngram counts and uses a **priority queue** to return the k most common words.

## What I learned
- Choosing the right map (hash vs. sorted tree) depends on whether order matters.
- Real datasets like WordNet need indexes built up front so queries stay fast.
- Combining two datasets (a graph and a time series) is where the interesting answers come from.

## Skills and tools
Java, HashMap, TreeMap, HashSet, PriorityQueue, directed graphs, depth-first traversal, recursion, time-series aggregation, file parsing, top-k queries, JUnit, client-server query handlers.
