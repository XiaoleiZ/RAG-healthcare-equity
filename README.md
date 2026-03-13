# FDA Events RAG with Stock Price

Simple RAG system: FDA Drug approval data → embeddings → stock prices → LLM answers

## Quick Start

1. **Data**: Download [FDA Drug Approval data](https://www.accessdata.fda.gov/scripts/cder/daf/) and save as `DrugsFDA_FDA-Approved_Drugs_March2026.csv`
2. **API Key**: `export GROQ_API_KEY="your-key"`
3. **Run**: Open notebook in Jupyter and run cells (packages install automatically)

## Example

```python
answer, results = ask_question("FDA events for Johnson and Johnson?", stock="JNJ")
print(answer)
```
Outputs: 
```python
On March 5, 2026, Johnson and Johnson's subsidiary, Janssen Biotech, received FDA approvals for
three new treatments: Erleadanda, Talveybla, and Tecvaylibla. The stock price of Johnson and Johnson
moved downward on the approval dates, with a price change of -3.00% for each of the approved
treatments. This suggests that the market may have been expecting more significant or positive
outcomes from these approvals, leading to a slight decline in the stock price.

================================================================================
Approval Date	Company	ticker	Drug Name	Submission Status	Price Change
44	2026-03-05	JANSSEN BIOTECH	JNJ	ERLEADANDA   #210951	Approval	-3.0
52	2026-03-05	JANSSEN BIOTECH	JNJ	TALVEYBLA   #761342	Approval	-3.0
51	2026-03-05	JANSSEN BIOTECH	JNJ	TECVAYLIBLA   #761291	Approval	-3.0
`
```

## What It Does

- Loads FDA drug approval data
- Converts company names to stock tickers
- Uses embeddings to search FDA events
- Fetches stock prices on approval dates
- Generates answers with LLM
