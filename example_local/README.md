Note that this folder was generated with an older version of example.ipynb that used ministral-3:8b through Ollama


Old fix code 

```python
# Fix decisions for the spots where the model correctly answered but didn't follow pairadigm's formatting instructions
p.pairwise_df['decision'] = p.pairwise_df['justification'].str.extract(r"FINAL ANSWER:\s*.*?(Description 1|Description 2|Tie).*?")

p.pairwise_df['decision'] = p.pairwise_df['decision'].replace({
    'Description 1': 'Text1',
    'Description 2': 'Text2'
})

p.pairwise_df
```