# ScratchChat

**ScratchChat** is a secure, privacy max decentralised demo for chatting over the Autonomi peer-to-peer network. It's a bit like Twitter/X and other social media in that you only see things from people you follow, but the UI is more like a chat interface.
![Screenshot of Swagger UI](./misc/scratchchat-screenshot-1.png?raw=true "screenshot of early ScratchChat")


It's main purpose is not a great chat experience, but a way to have fun while demonstrating how to use the dweb RESTful API to build apps for Autonomi. It also demonstrates using the Scratchpad data type which is paid for to create but free to update after that.

The app consists of a single 64kB HTML file which creates two ScratchPads when first used, to store your settings and share your messages. Once that is done further use is free so you can share addresses and add them to your follows. Here's mine (live on Autonomi now).

If you upload an avatar image to Autonomi you can paste the address into the UI and save it by clicking the "Save Changes" button.

Decentralised web apps like ScratchChat are regular static websites published to Autonomi using **dweb**, but become **dynamic websites** when using the dweb **RESTful HTTP API**.

After installing dweb, anyone can use decentralised web apps and websites work in a **standard web browser** without any special plugins, configuration or changes by a user.

For more, including how to build apps like ScratchChat, see [dweb](https://github.com/happybeing/dweb/blob/main/dweb-cli/README.md#dweb-command-line-app).

## Try ScratchChat on Autonomi
You will need an Autonomi compatible wallet setup in your terminal, with a tiny amount of ARB-ETH and ANT to pay for creation of two Scratchpads on the Autonomi network. This will be a few cents/pennies and only happens when you first load ScratchChat. After that there's no more to pay. Oh, and you are paying the Autonomi network, not me!

For now, you give `dweb` access to your wallet my setting the environment variable SECRET_KEY to the secret for your wallet.

Once you have a wallet, install the `dweb` command:
```
cargo install dweb-cli --locked
```
If you aren't sure what the above means see [here](https://github.com/happybeing/dweb/tree/main/dweb-cli#browse-the-dweb). Once you have the dweb command, start your local server:

```
dweb serve
```
Then in another terminal, this will instruct the server to launch Scratchchat:
```
dweb open 40ea2e530a60645363ae561c8a50c165f79d8a034c4458f68f1b848c11386e45
```
Once your browser opens, wait a few minutes while ScratchChat starts for the first time and soon you'll be up and chatting... as soon as you find someone to follow and chat with!

## Web App Developers
To start building your own decentralised app for Autonomi see the dweb documentation: [Develop a Decentralised Web App](https://github.com/happybeing/dweb/blob/main/dweb-cli/README.md#develop-a-decentralised-web-app).

## LICENSE

Everything is licensed under AGPL3.0 unless otherwise stated. Any contributions are accepted on the condition they conform to this license.

See also [./LICENSE](./LICENSE)
