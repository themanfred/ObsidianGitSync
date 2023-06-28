## Sentiment (positive/negative)

	lamp_review = """
	Needed a nice lamp for my bedroom, and this one had \
	additional storage and not too high of a price point. \
	Got it fast.  The string to our lamp broke during the \
	transit and the company happily sent over a new one. \
	Came within a few days as well. It was easy to put \
	together.  I had a missing part, so I contacted their \
	support and they very quickly got me the missing piece! \
	Lumina seems to me to be a great company that cares \
	about their customers and products!!
	"""

## Doing multiple tasks at once
	prompt = f"""
	Identify the following items from the review text: 
	- Sentiment (positive or negative)
	- Is the reviewer expressing anger? (true or false)
	- Item purchased by reviewer
	- Company that made the item
	
	The review is delimited with triple backticks. \
	Format your response as a JSON object with \
	"Sentiment", "Anger", "Item" and "Brand" as the keys.
	If the information isn't present, use "unknown" \
	as the value.
	Make your response as short as possible.
	Format the Anger value as a boolean.
	
	Review text: '''{lamp_review}'''
	"""
	response = get_completion(prompt)
	print(response)
## Make a news alert for certain topics

	prompt = f"""
	Determine whether each item in the following list of \
	topics is a topic in the text below, which
	is delimited with triple backticks.
	
	Give your answer as a JSON object with each topic list " as the keys. with 0 or 1 for each topic.\
	
	List of topics: {", ".join(topic_list)}
	
	Text sample: '''{story}'''
	"""
	response = get_completion(prompt)
	print(response)
topic_dict = {i.split(': ')[0]: int(i.split(': ')[1]) for i in response.split(sep='\n')}
if topic_dict['nasa'] == 1:
    print("ALERT: New NASA story!")