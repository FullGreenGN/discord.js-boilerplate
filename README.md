# Discord.js v14.17.3 TypeScript Boilerplate

A robust boilerplate to kickstart your Discord bot development using Discord.js v14 and TypeScript.

## Features

- **Command Handling**: Modular and dynamic command loading.
- **Event Handling**: Easy-to-manage event listeners.
- **TypeScript Support**: Type-safe development with TypeScript.
- **Environment Variables**: Secure token management with `dotenv`.
- **Linting and Formatting**: ESLint and Prettier pre-configured for clean code.
- **Logging**: Integrated `winston` logger for debugging.

## Prerequisites

- Node.js v16.9.0 or newer
- npm or yarn
- A Discord bot token ([Get it here](https://discord.com/developers/applications))

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/fullgreengn/discord.js-boilerplate.git
   cd discord-bot-boilerplate
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Create a `.env` file in the root directory:
   ```plaintext
   BOT_TOKEN=your-discord-bot-token
   ```

4. Start the bot:
   ```bash
   npm start
   ```

## Project Structure

```
discord-bot-boilerplate/
├── src/
│   ├── commands/       # Slash commands
│   │   └── ping.ts     # Example command
│   ├── events/         # Event listeners
│   │   └── ready.ts    # Example event
│   └── index.ts        # Entry point
├── node_modules/       # Installed dependencies
├── .env                # Environment variables
├── package.json        # Project metadata
├── tsconfig.json       # TypeScript configuration
└── README.md           # Project documentation
```

## Commands

Place your slash commands in the `src/commands` folder. Here's an example:

**`ping.ts`:**
```typescript
import { SlashCommandBuilder } from 'discord.js';

export const data = new SlashCommandBuilder()
  .setName('ping')
  .setDescription('Replies with Pong!');

export const execute = async (interaction: any) => {
  await interaction.reply('Pong!');
};
```

## Events

Place event listeners in the `src/events` folder. Here's an example:

**`ready.ts`:**
```typescript
import { Client } from 'discord.js';

export const name = 'ready';
export const once = true;
export const execute = (client: Client) => {
  console.log(`Logged in as ${client.user?.tag}!`);
};
```

## Contributing

Feel free to fork the repository and submit pull requests. Contributions are welcome!

## License

This project is licensed under the [MIT License](LICENSE).