"""
AI Trainer Sample - Code Evaluation & Prompt Engineering
Author: Vinicius Alves | Outlier Top Rated (4.29/5)
"""

def evaluate_ai_response(prompt, response):
    """Simulates the evaluation task we do at Outlier"""
    score = 0
    checks = {
        "relevance": len(response) > 20,
        "clarity": "." in response,
        "no_hallucination": "as an AI" not in response.lower()
    }
    
    for check, passed in checks.items():
        if passed:
            score += 1
            print(f"✅ {check}: PASS")
        else:
            print(f"❌ {check}: FAIL")
    
    return f"Final Score: {score}/{len(checks)}"

# Example - SQL Evaluation Task (Outlier style)
prompt = "Write a SQL query to find top 5 users by orders"
ai_response = "SELECT user_id, COUNT(*) as total FROM orders GROUP BY user_id ORDER BY total DESC LIMIT 5;"

print(evaluate_ai_response(prompt, ai_response))
print("\nQuery is correct and follows best practices!")
