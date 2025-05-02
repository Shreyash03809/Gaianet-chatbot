import requests

API_KEY = "gaia-MjRmY2Y1NDItZjg5Yy00Mjk3LTgzYWQtMjFhOTczNTg3NDcy-xnw8ffbkP0rl_Qh1"
API_URL = "https://llama.gaia.domains/v1/chat/completions"

def chat():
    print("GaiaNet Chatbot (type 'exit' to quit)")
    messages = [
        {"role": "system", "content": "You are a helpful AI assistant powered by GaiaNet."}
    ]

    while True:
        user_input = input("You: ")
        if user_input.lower() == "exit":
            break

        messages.append({"role": "user", "content": user_input})

        response = requests.post(
            API_URL,
            headers={
                "Authorization": f"Bearer {gaia-MjRmY2Y1NDItZjg5Yy00Mjk3LTgzYWQtMjFhOTczNTg3NDcy-xnw8ffbkP0rl_Qh1}",
                "Content-Type": "application/json"
            },
            json={
                "model": "llama",
                "messages": messages
            }
        )

        if response.status_code == 200:
            reply = response.json()["choices"][0]["message"]["content"]
            print("Bot:", reply)
            messages.append({"role": "assistant", "content": reply})
        else:
            print("Error:", response.status_code, response.text)

if name == "main":
    chat()
