# cmd
work


import random

class ChatBot:
    def __init__(self, name):
        self.name = name
        self.responses = {
            "hi": ["Hello!", "Hi there!", "Greetings!"],
            "how are you": ["I'm just a bot, but I'm doing great!", "I'm here to assist you.", "Feeling like a million lines of code!"],
            "bye": ["Goodbye!", "See you later!", "Take care!"],
            "default": ["Sorry, I don't understand that.", "Can you rephrase?", "I'm not sure how to respond to that."]
        }

    def get_response(self, message):
        message = message.lower()
        for key in self.responses:
            if key in message:
                return random.choice(self.responses[key])
        return random.choice(self.responses["default"])

    def chat(self):
        print(f"Hello! I am {self.name}, your chat assistant.")
        print("Type 'bye' to end the chat.")
        
        while True:
            user_message = input("You: ")
            if user_message.lower() == "bye":
                print(f"{self.name}: {random.choice(self.responses['bye'])}")
                break
            response = self.get_response(user_message)
            print(f"{self.name}: {response}")

if __name__ == "__main__":
    bot_name = input("Enter the bot's name: ")
    bot = ChatBot(bot_name)
    bot.chat()
