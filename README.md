# ElasticSearh
## Set up 
1. Make sure to install [Docker](https://www.docker.com/products/docker-desktop/) in your local environment.
2. Run the following command: ```docker-compose up```

## Topics
### Score
- Match a document with the search
- Algorithm vefifies:
	- Number of occurrences / unique words
	- Results sorted by the **score** as default

### Clausules
#### Introducction
- Common clausules: **Must**, **Filter**, **Should** and **Must not**
- For a single query:
	- Use **{}** (an object)
- For more than 2 queries:
	- Use **[]** (a list of objects)

#### Must
- **AND** logic
- The query **must** appear in the documents returned.
- **Score** is so important.

#### Filter
- **AND** logic too
- The query **must** appear in the documents returned.
- Score **isn't** important.
- Use **Filter** insted of **Must** when the **score** isn't important for us.
- Allow cache

#### Should
- **Or** logic
- Some of the queries **must** appear in the documents retorned.
- **Score** is important.
- **minimum_should_match** allow encourage the behaviour of how many queries must match.
- If **Must** or **Filter** (AND) are present in the sub query **minimum_should_match=0** (by default); **Should** became optional
	Otherwise **minimum_should_match=1** (by default)

	#### Must Not
	- **NOt** logic
	- Query **must not** appear in the documents retorned
	- **No** affect to the **score**
	- Allow cache