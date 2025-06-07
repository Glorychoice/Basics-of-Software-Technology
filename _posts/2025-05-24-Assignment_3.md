## Report Summary
- Assignment 3 focused on the deployment and integration of Large Language Models (LLMs) in both online and offline environments. The core objective was to understand how to leverage AI models like OpenAI's GPT-4 for cloud-based interaction and locally deployed models like Meta’s LLaMA3 using the Ollama framework. Ollama provides a simple and efficient way to run powerful LLMs locally without requiring internet access, making it ideal for offline development tasks. During this assignment, I installed Ollama, deployed the LLaMA3 model, and verified its functionality through terminal prompts. I also integrated local (Ollama + LLaMA3) models into my development environment (VSCode). belowbis the code:

- import requests

print("Script started...")  # Always prints at the beginning

prompt = "tell my reasons GNSS is very important in the world."

try:
    print("Sending request to Ollama...")
    response = requests.post(
        'http://localhost:11434/api/generate',
        json={
            "model": "llama3",
            "prompt": prompt,
            "stream": False
        }
    )

    print("Status Code:", response.status_code)

    if response.status_code == 200:
        print("Ollama says:", response.json()["response"])
    else:
        print("Ollama returned error:", response.text)

except Exception as e:
    print("Exception occurred:", e)

- This practical shows how LLMs can significantly boost productivity in programming and research, offline using OLLAMA - LLAMA3.
  
## conclusion
- Online Model API: I actually installed and got my API Key but could not use it but i so used Ollama because is fast and it offline, i mean without Internet and other benefits.
- Local Model Deployment: Ollama - llama3
- Integration into Development Environment: VSCode

# References
- OpenAI API
- Ollama
- VSCode
- Python

