
![[Pasted image 20230517215649.png]]

	def get_completion_from_messages(messages, model="gpt-3.5-turbo", temperature=0):
    response = openai.ChatCompletion.create(
        model=model,
        messages=messages,
        temperature=temperature, # this is the degree of randomness of the model's output
    )
    print(str(response.choices[0].message))
    return response.choices[0].message["content"]

The system sets or helps the assistant understand its role and how to interact better with it's user.

