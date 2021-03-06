# Nextcloud Talk library in TypeScript for Deno

[![deno doc](https://doc.deno.land/badge.svg)](https://doc.deno.land/https/deno.land/x/talk_lib/mod.ts)


The purpose of this repository is to provide an easy way to make bots for Nextcloud Talk

## Example script

To set it up, copy `example.env` into `.env` and replace the values with the proper information.

To start, run `deno run --allow-net --allow-read example.ts`

## Basic example

A basic example of this would look like
```TypeScript
import { Client, Message } from "https://raw.githubusercontent.com/JipFr/talk-lib/master/mod.ts";

const options = {
  username: "my.username",
  password: "myPassword123",
  url: "nc.mywebsite.com"
};

const client = new Client(options);

client.on("message", (evt: Message) => {
    console.log(`${evt.author.name}: ${evt.content}`);
});

client.start().then(() => {
	console.log("Started.");
});
```
