# Nextcloud Talk library in TypeScript for Deno

The purpose of this repository is to provide an easy way to make bots for Nextcloud Talk

To set it up, copy `example.env` into `.env` and replace the values with the proper information.

To start, run `deno --allow-net --allow-read main.ts`

## Basic example

A basic example of this would look like
```TypeScript
import Talk, { Message } from "./Talk/main.ts";

const options = {
  username: "my.username",
  password: "myPassword123",
  url: "nc.mywebsite.com"
};

const client = new Talk(options.url);

client.on("message", (evt: Message) => {
    console.log(`${evt.author.name}: ${evt.content}`);
});

client.login(options.username, options.password);
client.start();
```