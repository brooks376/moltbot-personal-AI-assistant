
# Moltbot personal AI assistant

Moltbot is your **personal AI assistant** that runs on your own devices, not in someone else’s cloud. It connects to the chat apps you already use and can automate almost anything you can do on your computer.

## Overview

Moltbot runs on [macOS](https://www.apple.com/os/macos/), Linux, and Windows (via WSL2) and talks to you through familiar channels like [WhatsApp](https://www.whatsapp.com/) Telegram, Slack, Discord, Google Chat, Signal, iMessage (via BlueBubbles), Microsoft Teams, Matrix, Zalo, Zalo Personal, and WebChat. It feels like a fast, local, always‑on teammate you reach simply by sending a message.

Instead of being locked into a hosted SaaS, Moltbot lives alongside your tools and data. It can read and write files, run shell commands, control your browser, and orchestrate applications, so it can actually take action on your behalf—not just reply with text. Over time it builds up long‑term memory of your preferences, projects, and routines, so it becomes uniquely tuned to you instead of behaving like a generic chatbot.

Because it is open source and extensible, you can wire in your preferred models (Anthropic, OpenAI, or others), add custom skills and plugins, and even let Moltbot design and iterate on new skills for itself. The goal is to feel like a personal “OS layer” on top of your existing stack, quietly running in the background and stepping in whenever you need help.

## Key Features

- **Runs on your own devices**  
  Install on macOS, Linux, or Windows (via WSL2) so you stay in control of your data and environment.

- **Any chat app, one assistant**  
  Talk to Moltbot from WhatsApp, Telegram, Slack, Discord, Google Chat, Signal, iMessage (via BlueBubbles), Microsoft Teams, Matrix, Zalo, Zalo Personal, or WebChat, in DMs or group chats.

- **Persistent long‑term memory**  
  Moltbot remembers what matters: your projects, preferences, and history, so you don’t have to repeat yourself.

- **Full system & browser control**  
  It can work with your filesystem, shell, and browser to run workflows, fill in forms, and automate multi‑step tasks.

- **Skills and plugins**  
  Extend Moltbot with community skills or write your own to integrate with APIs, tools, and internal systems.

## Getting Started

The recommended way to get started is to run the interactive onboarding wizard. It will guide you through setting up the gateway, workspace, channels, and skills.

### Prerequisites

- Node.js 22 or higher  
- npm, pnpm, or bun (any of them works)  
- Access to your preferred model providers (for example Anthropic or OpenAI)

### Installation

Clone the repository and install dependencies:

```bash
git clone https://github.com/moltbot/moltbot.git
cd moltbot

# pick one:
npm install
# or
pnpm install
# or
bun install
```

### Onboarding Wizard

Run the onboarding wizard to configure Moltbot and optionally install it as a daemon:

```bash
moltbot onboard --install-daemon
```

The wizard will help you:

- Configure the gateway
- Set up your workspace
- Connect channels (WhatsApp, Telegram, Slack, Discord, Google Chat, Signal, iMessage/BlueBubbles, Microsoft Teams, Matrix, Zalo, Zalo Personal, WebChat)
- Enable and configure skills

### Run the Gateway

Once onboarding is complete, start the gateway:

```bash
moltbot gateway --port 18789 --verbose
```

You can customize the port and verbosity flags as needed.

## Basic Usage

### Send a Message

You can send a message to a specific recipient (for example, a phone number connected through a channel) from the CLI:

```bash
moltbot message send \
  --to +1234567890 \
  --message "Hello from Moltbot"
```

This will deliver the message through the configured channel (such as WhatsApp or SMS via your setup).

### Talk to the Assistant

To talk directly to your assistant from the CLI and optionally have the response forwarded back to any connected channel:

```bash
moltbot agent \
  --message "Ship checklist" \
  --thinking high
```

With channels connected, Moltbot can deliver the conversation back into WhatsApp, Telegram, Slack, Discord, Google Chat, Signal, iMessage/BlueBubbles, Microsoft Teams, Matrix, Zalo, Zalo Personal, or WebChat.

## Example Workflows

- Ask Moltbot from Telegram to summarize your inbox, draft replies, and schedule follow‑ups.  
- Trigger a “daily brief” from WhatsApp that pulls calendar events, reminders, and key metrics into a single message.  
- From Discord, have Moltbot run tests, inspect logs, and propose fixes or PR descriptions for your codebase.

## Configuration & Docs

For detailed configuration, channel‑specific setup, updating instructions, and advanced examples, see:

- Website: https://moltbot.you/ 
- Github：https://github.com/moltbot/moltbot

## Contributing

Contributions are welcome—whether it’s new skills, integrations, bug fixes, or docs improvements. Feel free to open an issue or submit a pull request and help make Moltbot an even better personal AI assistant.
