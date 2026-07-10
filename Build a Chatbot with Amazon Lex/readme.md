# 🤖 Build a Chatbot with Amazon Lex

Welcome! 👋

This project demonstrates how to build a simple AI chatbot using **Amazon Lex**. The chatbot, called **BankerBot**, can greet users, understand basic conversations, and respond to both text and voice inputs.

This project is perfect for beginners who want to learn how Amazon Lex works and how conversational AI is built on AWS.

---

# 📌 Project Overview

In this project, I created a chatbot named **BankerBot** using **Amazon Lex V2**.

The chatbot can:

- 👋 Greet users
- 💬 Understand simple user messages
- 🎤 Accept both text and voice input
- 🤖 Detect user intent
- ❓ Handle unknown requests using FallbackIntent

---

# 🏗️ AWS Services Used

- Amazon Lex V2
- AWS IAM

---

# 📚 What I Learned

After completing this project, I learned how to:

- Create a chatbot using Amazon Lex
- Create intents
- Add sample utterances
- Configure chatbot responses
- Build and test a chatbot
- Handle unknown user inputs with FallbackIntent
- Use voice conversations
- Understand Intent Classification Confidence Score

---

# 🧠 What is Amazon Lex?

Amazon Lex is an AWS service used to build intelligent chatbots.

It uses:

- Artificial Intelligence (AI)
- Natural Language Processing (NLP)
- Automatic Speech Recognition (ASR)

to understand what users are saying and respond naturally.

It supports:

- Text conversations
- Voice conversations

Examples:

- Banking chatbot
- Customer support
- Food ordering
- Appointment booking
- Help desk assistant

---

# 🚀 Project Architecture

```
User
   │
   ▼
Amazon Lex (BankerBot)
   │
   ▼
Intent Detection
   │
   ├────────────► WelcomeIntent
   │
   └────────────► FallbackIntent
   │
   ▼
Chatbot Response
```

---

# ⚙️ Step 1 - Create the Chatbot

Navigate to:

```
AWS Console
      ↓
Amazon Lex V2
      ↓
Create Bot
      ↓
Blank Bot
```

Bot Details:

| Setting | Value |
|---------|-------|
| Bot Name | BankerBot |
| Description | Banker Bot to help customer check their balance and make transfers |
| IAM Role | Create a role with basic Amazon Lex permissions |
| Error Logging | Disabled |
| COPPA | No |
| Session Timeout | 5 Minutes |

---

# 🎤 Voice Settings

Language:

```
English (US)
```

Voice:

Choose any Amazon Polly voice.

Example:

- Danielle
- Gregory
- Ruth

---

# 🎯 Intent Classification Confidence Score

Confidence Score:

```
0.40
```

This means:

If Lex is **40% confident** that it understands the user's request, it will trigger the matching intent.

Otherwise,

it will trigger **FallbackIntent**.

---

# 💬 Step 2 - Create WelcomeIntent

Intent Name

```
WelcomeIntent
```

Description

```
Welcoming a user when they say hello.
```

---

# 📝 Sample Utterances

These are the phrases users can say.

```
Hi

Hello

I need help

Can you help me?
```

Whenever a user says something similar,

Amazon Lex triggers **WelcomeIntent**.

---

# 💬 Welcome Response

```
Hi! I'm BB, the Banking Bot.
How can I help you today?
```

---

# 🧪 Testing the Chatbot

After building the chatbot, test it using messages like:

```
Hello

Hi

Help me

Hiya
```

These should trigger:

```
WelcomeIntent
```

---

# ❌ Unknown Messages

If the chatbot doesn't understand something like:

```
Good morning

What's today's weather?

Tell me a joke
```

Amazon Lex activates:

```
FallbackIntent
```

---

# ⚠️ What is FallbackIntent?

FallbackIntent is the chatbot's default response whenever it cannot understand the user's request.

Instead of returning an error,

the chatbot politely asks the user to try again.

---

# ✍️ Fallback Response

```
Sorry, I am having trouble understanding.

Can you describe what you'd like to do in a few words?

I can help you find your account balance, transfer funds and make a payment.
```

---

# 🔄 Response Variations

Amazon Lex can randomly choose different responses.

Example:

```
Hmm, could you try rephrasing that?

I can help you find your account balance,
transfer funds and make a payment.
```

This makes conversations sound more natural.

---

# 🎤 Voice Testing

Amazon Lex also supports voice conversations.

Click the microphone icon and say:

```
Hello
```

or

```
Hi
```

The chatbot converts your speech into text and replies automatically.

---

# 📸 Project Screenshots

Include screenshots like:

- Chatbot configuration
- WelcomeIntent
- Sample Utterances
- Voice settings
- Successful chatbot response
- FallbackIntent response
- Testing window

Example:

```
images/
│
├── chatbot-setup.png
├── welcome-intent.png
├── testing.png
├── fallback-response.png
```

---

# 📁 Project Structure

```
Amazon-Lex-Chatbot/
│
├── README.md
├── images/
│   ├── chatbot-setup.png
│   ├── testing.png
│   ├── fallback-response.png
│   └── welcome-intent.png
```

---

# 💡 Key Concepts

## Amazon Lex

AWS service used for building conversational AI chatbots.

---

## Intent

An intent represents what the user wants.

Example:

```
Check balance

Transfer money

Say hello
```

---

## Utterance

An utterance is an example sentence spoken by the user.

Example:

```
Hi

Hello

Can you help me?
```

---

## Response

The message the chatbot sends back after understanding the user's request.

---

## FallbackIntent

The default intent that runs when Lex cannot understand the user's message.

---

## Confidence Score

A value between **0 and 1** that represents how confident Lex is in identifying the correct intent.

---

# 🎯 Skills Gained

- Amazon Lex
- Conversational AI
- AWS Chatbot Development
- Intent Configuration
- Utterance Design
- Voice Chatbots
- AI Basics
- AWS IAM
- Testing and Debugging

---

# 🧹 Clean Up

To avoid AWS charges:

- Delete the Amazon Lex Bot
- Delete unused IAM roles (if created only for this project)

Always clean up AWS resources after completing your lab.

---

# 📖 Conclusion

In this project, I built my first AI chatbot using Amazon Lex.

I learned how to create intents, configure chatbot responses, test conversations using text and voice, and improve user experience with FallbackIntent responses.

This project provides a strong foundation for building more advanced conversational AI applications on AWS.

---

# 👨‍💻 Author

**Mudasir Ahmad**

GitHub: https://github.com/mudasiranberlin

---

# ⭐ If you found this project helpful

Give this repository a ⭐ on GitHub!
