# This repository has moved

This repository has been migrated from Microsoft Github to the EU based non-profit Codeberg.org where members have a say and contributors to Open Source software are not farmed like cattle.

You will find this and my other repositories at https://codeberg.org/happybeing

# ScratchChat

**ScratchChat** is a secure, privacy max decentralised demo for chatting over the Autonomi peer-to-peer network. It's a bit like Twitter/X and other social media in that you only see things from people you follow, but the UI is more like a chat interface.
![Screenshot of Swagger UI](./misc/scratchchat-screenshot-1.png?raw=true "screenshot of early ScratchChat")


It's main purpose is not a great chat experience, but a way to have fun while demonstrating how to use the **[dweb REST API](https://github.com/happybeing/dweb/tree/main/dweb-cli#web-api)** to build apps for Autonomi. It also demonstrates using the **Scratchpad data type** which is paid for to create but free to update after that. So **messaging is free once** ScratchChat has been run for the first time!

The app consists of a single 64kB HTML file which creates two Scratchpads when first used, to store your settings and share your messages. Once that is done further use is free so you can share addresses and add them to your follows. Here's mine (live on Autonomi now).

If you upload an avatar image to Autonomi you can paste the address into the UI and save it by clicking the "Save Changes" button.

### Published using dweb
Decentralised web apps like ScratchChat are regular static websites published to Autonomi using **[dweb](https://github.com/happybeing/dweb/tree/main/dweb-cli#dweb-command-line-app)**, but become **dynamic websites** when using the dweb **[dweb REST API](https://github.com/happybeing/dweb/tree/main/dweb-cli#web-api)**.

After installing dweb, anyone can view and use decentralised web apps and websites in a **standard web browser** without any plugins, configuration or other changes by the user.

For more, including how to build apps like ScratchChat, see [dweb](https://github.com/happybeing/dweb/blob/main/dweb-cli/README.md#dweb-command-line-app).

## Try ScratchChat on Autonomi
You will need an Autonomi compatible wallet setup in your terminal, with a tiny amount of ARB-ETH and ANT to pay for creation of two Scratchpads on the Autonomi network. This will be a few cents/pennies and only happens when you first load ScratchChat. After that there's no more to pay. Oh, and you are paying the Autonomi network, not me!

To get chatting:

- Get Rust
- Setup a Wallet
- Install dweb-cli
- Use ScratchChat
- Find People to chat with

Note that most of these steps only have to be done once. Afterwards you will be able to view and publish decentralised websites and use other websites and apps direct from Autonomi. And if you only want to view you will only need dweb, not a wallet.

### Get Rust
If you don't have Rust you will need to install that first - see [Get Rust](https://github.com/happybeing/dweb/tree/main/dweb-cli#get-rust). Later I will provide builds so you won't need to install Rust but for now you have to do it this way.

### Set up a Wallet
You will need a wallet if you wish to upload data to Autonomi, or use a web application which stores data on the network.

You don't need a wallet just to browse websites or download files published by others. If you want to upload data, you can set-up your wallet as follows.

1. Check if you have a wallet using the `ant-cli` (install with `cargo install ant-cli --locked` if you don't have that yet):
   ```
   ant wallet balance
   ```
2. If you don't have a wallet yet, create it with `ant wallet create` or import an existing wallet for which you already have the private key, with `ant wallet import`

3. If you don't have funds, head over to the [Autonomi Community Faucet](https://forum.autonomi.community/t/community-faucet-live/41299?u=ambled)

If you need help with this, see the help and support sections of `autonomi.com`:
- User focussed documentation ([docs.autonomi.com](https://docs.autonomi.com))
- Autonomi support ([Discord](https://discord.gg/autonomi))
- Community forum ([Discourse](https://forum.autonomi.community/))

Payment is handled automatically, and you can check the cost beforehand using `dweb cost` as follows:
```
dweb cost --files-root blog
```
At the time of writing the cost is not accurately reported by the Autonomi network, but is usually very cheap compared to cloud storage. Especially as your data will be stored for the lifetime of the Autonomi network at no extra cost.

#### SECRET_KEY variable
By default dweb will use the wallet you created or imported with the `ant` command (see above). If you have set a password for this, dweb will ask you for that so it can unlock the wallet when you run `dweb serve`. For some users and developers you can use a different wallet by setting the `SECRET_KEY` environment variable to the value of a wallet secret key. When `SECRET_KEY` is set, dweb will use this instead.

On Linux and MacOS you can either put `export SECRET_KEY=<PRIVATE-KEY>` in your `.bashrc` and then *open a new terminal*, or pass it when you start the dweb server with:
   ```
   export SECRET_KEY=<PRIVATE-KEY> dweb serve
   ```

### Install dweb-cli
`dweb` provides a local server with REST API to Autonomi which ScratchChat and other web apps can use to access the peer-to-peer network from a standard web application. It is also able to publish and update websites that you create on Autonomi, and will open them in a regular browser with a simple command such as `dweb open awesome` which opens a website with links to other websites on Autonomi. (Learn [more about dweb](https://github.com/happybeing/dweb/tree/main/dweb-cli#dweb-command-line-app))

Assuming you have Rust installed (if not see [Get Rust](https://github.com/happybeing/dweb/tree/main/dweb-cli#get-rust)) you can install dweb with:
```
cargo install dweb-cli --locked
```
Note: when installing dweb on Ubuntu, you may encounter missing openssl libraries. Do a `sudo apt update` and then `sudo apt install librust-openssl-dev`, and finally restart the dweb install.

Once you have `dweb` installed you'll be able to find other websites and apps in the **awesome index** with `dweb open awesome`.

### Use ScratchChat
If you have a funded wallet and `dweb` installed, start the dweb server:
```
dweb serve
```
In a different terminal, open ScratchChat:
```
dweb open scratchchat
```
When ScratchChat loads for the first time, it creates two Scratchpads to store your settings and share your messages, and then shows your address in the UI.

You need to add someone's ScratchChat address as a 'follow' to see their messages, and they need to add your address to see yours. So post your address in this [forum topic](https://forum.autonomi.community/t/scratchchat-join-the-chatters-and-post-your-address-on-this-topic/41776?u=happybeing) if you want others to follow and chat with you.

ScratchChat works more like a social network such as Mastodon or Twitter, but with a chat style interface.

#### Messaging is free!
Although you need a wallet with a tiny amount of ARB-ETH and ANT to pay for the creation of two Scratchpads, that's it (current cost about 2 cents). And thanks to [@ambled](https://forum.autonomi.community/u/ambled/summary) who made the [Autonomi Community Faucet](https://forum.autonomi.community/t/community-faucet-live/41299?u=ambled) and some generous donors, you can get enough tokens to do all that for free. (See [Set up a Wallet](https://forum.autonomi.community/t/scratchchat-join-the-chatters-and-post-your-address-on-this-topic/41776?u=happybeing#p-416361-set-up-a-wallet-1)).

Scratchpads cost more to create than a regular 'chunk' stored on Autonomi, and this pays for them to be updated for free. But they are still very cheap - about 2 cents right now, which seems appropriate :-).

The [Autonomi Community Faucet](https://forum.autonomi.community/t/community-faucet-live/41299?u=ambled) can be used to start your journey by issuing your initial funds. You should receive enough funds to create your Scratchpads and upload a small image to use as your avatar.

### Find People to chat with

You'll find the Scratchchat addresses of some people to chat with, including my own, at the end of [this post](https://forum.autonomi.community/t/scratchchat-join-the-chatters-and-post-your-address-on-this-topic/41776?u=happybeing) on the Autonomi forum and you can share your own address on that topic so others can follow you to see what you write.

## Web App Developers
To start building your own decentralised app for Autonomi see the dweb documentation: [Develop a Decentralised Web App](https://github.com/happybeing/dweb/blob/main/dweb-cli/README.md#develop-a-decentralised-web-app).

## Contributions
Contributions under the AGPL3.0 license are welcome and any contributions or PRs submitted will be assumed to be offered under that license unless clearly and prominently specified otherwise. Any contributions are accepted on the condition they conform to that license and the following conditions:

- that by submitting a contribution you are confirming that you are the sole author, understand all the submitted code in depth, and that no AI or other code generation tool that has ingested copyright material was used in generating content in your contribution.

Thanks for understanding that I don't want to accept material of unknown provenance nor spend time reviewing code that the contributor doesn't understand completely.

## LICENSE

Everything is licensed under AGPL3.0 unless otherwise stated.

See also [./LICENSE](./LICENSE)
