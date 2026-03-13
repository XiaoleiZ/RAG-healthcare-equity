# FDA Events RAG with Stock Price

Simple RAG system: FDA data → embeddings → stock prices → LLM answers

## Quick Start

1. **Data**: Download FDA data and save as `DrugsFDA_FDA-Approved_Drugs_March2026.csv`
2. **API Key**: `export GROQ_API_KEY="your-key"`
3. **Run**: Open notebook in Jupyter and run cells (packages install automatically)

## Example

```python
answer, results = ask_question("FDA events for Johnson and Johnson?", stock="JNJ")
print(answer)
```

## What It Does

- Loads FDA drug approval data
- Converts company names to stock tickers
- Uses embeddings to search FDA events
- Fetches stock prices on approval dates
- Generates answers with LLM
