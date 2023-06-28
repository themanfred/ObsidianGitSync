## Model Limitations: Hallucinations
- Boie is a real company, the product name is not real.
- 
prompt = f"""
Tell me about AeroGlide UltraSlim Smart Toothbrush by Boie
"""
response = get_completion(prompt)
print(response)


[[GPT-3]] or [[chatGPT]] can make things that sound realistic but do not exist so it is kind of dangerous.


There is a process or framework to make proper prompts

# Iterative Prompt Development

Idea, Implementation (code/data), Emperimental result, Error Analysis

Prompt guidelines
- be clear and specific
- analyze why result does not give desired  output
- Refine the idea and the prompt
- Repeat
![[Pasted image 20230517131317.png]]


## Issue 1: The text is too long 
- Limit the number of words/sentences/characters.
## Issue 2. Text focuses on the wrong details
- Ask it to focus on the aspects that are relevant to the intended audience.
## Issue 2. Text focuses on the wrong details
- Ask it to focus on the aspects that are relevant to the intended audience.
## Issue 3. Description needs a table of dimensions[](https://s172-31-5-231p59352.lab-aws-production.deeplearning.ai/notebooks/l3-iterative-prompt-development.ipynb#Issue-3.-Description-needs-a-table-of-dimensions)

-   Ask it to extract information and organize it in a table.
- After the description, include a table that gives the 
product's dimensions. The table should have two columns.
In the first column include the name of the dimension. 
In the second column include the measurements in inches only.

Give the table the title 'Product Dimensions'.

Format everything as HTML that can be used in a website. 
Place the description in a <div> element.