# Wk4
PART ONE
Q1: Explain how AI-driven code generation tools (e.g., GitHub Copilot) reduce development time. What are their limitations?
AI tools like GitHub Copilot help developers write code faster by:
1. Autocompleting code based on context, reducing the need to write repetitive or boilerplate code manually.
2. Suggesting functions or logic that align with common programming patterns, which speeds up problem-solving.
3. Assisting with unfamiliar languages or frameworks, allowing developers to stay productive without deep prior knowledge.
Limitations include:
1. Contextual misunderstanding: The AI may not fully grasp the specific requirements or architecture of a project.
2. Code quality concerns: It can generate insecure, inefficient, or non-idiomatic code that requires careful review.
3. Over-reliance risk: Developers might become dependent on suggestions, potentially weakening their problem-solving skills.

Q2: Compare supervised and unsupervised learning in the context of automated bug detection.
Supervised learning involves training a model on labeled data, where examples of buggy and clean code are clearly marked. This allows the model to learn patterns associated with known bugs and predict similar issues in new code. It’s effective when historical bug data is available.
Unsupervised learning, on the other hand, works with unlabeled data. It identifies anomalies or unusual patterns in code that may indicate bugs, even if those bugs haven’t been seen before. This is useful for detecting novel or rare issues.
Supervised learning is more accurate if the bug type is known while unsupervised learning helps discover unexpected or emerging issue.

Q3: Why is bias mitigation critical in AI-driven user experience personalization?
Bias mitigation is essential because AI systems trained on biased data can:
1. Deliver unfair or exclusionary experiences, such as recommending content that favors one group over another.
2. Reinforce harmful stereotypes, especially in sensitive areas like gender, race, or culture.
3. Erode user trust, leading to dissatisfaction or disengagement.
4.By actively addressing bias, organizations ensure that personalization is inclusive, ethical, and respectful of diverse user backgrounds and preferences, ultimately improving both user satisfaction and brand reputation.

PART TWO: How does AIOps improve software deployment efficiency? Provide two examples.
1. redict potential build failures before they occur.
Optimize test case execution by prioritizing those with higher success rates.
Dynamically allocate resources based on demand, reducing waste and improving performance.
Example:
Harness uses AI to automatically roll back failed deployments, minimizing downtime and reducing the need for manual intervention.

2. Automated Monitoring and Incident Management
AI-powered observability tools analyze logs, metrics, and traces in real time to detect anomalies and performance issues before they impact users. This proactive approach prevents critical failures and speeds up incident resolution.
Example:
Datadog and New Relic use AI to detect performance degradation early, while Splunk provides near real-time insights by correlating logs across systems.

PRACTICAL PART
My Python code
# Sample list of dictionaries
people = [
    {"name": "Alice", "age": 30},
    {"name": "Bob", "age": 25},
    {"name": "Charlie", "age": 35},
    {"name": "Diana"},  # Missing 'age' key
    {"name": "Eve", "age": 28}
]

# Function to sort by a specific key
def sort_dicts_by_key(data, sort_key):
    return sorted(data, key=lambda x: x.get(sort_key, float('inf')))

# Sort by 'age'
sorted_people = sort_dicts_by_key(people, "age")

# Print the sorted list
for person in sorted_people:
    print(person)
AI Suggested Code
# Sample list of dictionaries
people = [
    {"name": "Alice", "age": 30},
    {"name": "Bob", "age": 25},
    {"name": "Charlie", "age": 35},
    {"name": "Diana"},  # Missing 'age' key
    {"name": "Eve", "age": 28}
]

# Function to sort by a specific key
def sort_dicts_by_key(data, sort_key):
    return sorted(data, key=lambda x: x.get(sort_key, ''))

# Sort by 'age'
sorted_people = sort_dicts_by_key(people, "age")

# Print the sorted list
for person in sorted_people:
    print(person)
    
The manual implementation of the sorting function is designed with flexibility and robustness in mind. It uses Python’s built-in sorted() function along with a lambda expression that retrieves the sort key using .get(), providing a default value of float('inf') for missing keys. This approach ensures that dictionaries lacking the specified key do not cause runtime errors and are placed at the end of the sorted list. It is particularly effective in real-world scenarios where data may be incomplete or inconsistent. The use of float('inf') maintains type consistency, avoiding the common TypeError that arises when comparing strings and integers.

In contrast, the AI-suggested code includes a basic validation step that checks if the list is empty or if the first dictionary contains the sort key. It then proceeds to sort using direct key access (x[sort_key]). While this version may work well in controlled environments with uniform data, it is prone to failure if any dictionary is missing the key, resulting in a KeyError. This makes it less suitable for dynamic or unpredictable datasets.

Overall, the manual implementation is more efficient in terms of error handling and adaptability. It anticipates common data issues and resolves them gracefully, whereas the AI-suggested code assumes ideal conditions. For production-level applications or data pipelines, the manual version offers greater reliability and resilience, making it the preferred choice for developers working with diverse datasets.




















