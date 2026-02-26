# Simple Rule-Based Chatbot

def chatbot_response(user_input):
    user_input = user_input.lower()

    # Greeting responses
    if "hello" in user_input or "hi" in user_input:
        return "Hello! How can I help you today?"

    # Asking about chatbot
    elif "who are you" in user_input or "what are you" in user_input:
        return "I am a simple rule-based chatbot built using Python!"

    # Asking about weather
    elif "weather" in user_input:
        return "I can't fetch live weather, but you can check a weather app 🌦."

    # Asking about name
    elif "your name" in user_input:
        return "You can call me Chatbot 🤖."

    # Goodbye
    elif "bye" in user_input or "goodbye" in user_input:
        return "Goodbye! Have a great day ahead! 👋"

    # Default response
    else:
        return "Sorry, I don't understand that. Can you rephrase?"


# Run chatbot in loop
print("Chatbot: Hello! Type 'bye' to exit.")
while True:
    user_input = input("You: ")
    if "bye" in user_input.lower():
        print("Chatbot:", chatbot_response(user_input))
        break
    else:
        print("Chatbot:", chatbot_response(user_input))
