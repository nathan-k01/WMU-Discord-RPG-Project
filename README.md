# Phaser Discord Multiplayer Games Template

This project template is designed to be used in conjunction with our [Creating Multiplayer Discord Games with Phaser](https://phaser.io/tutorials/creating-multiplayer-discord-games-with-phaser) tutorial. It provides a starting point for creating multiplayer games on Discord with Colyseus and Phaser, utilising their new Embedded App SDK.

## Requirements

You need to have Node.js v21 or higher version.

## Template Project Structure

We have provided a default project structure to get you started. This is as follows:

- `packages/client` - Contains the game & Discord SDK source code.
- `packages/client/src/main.ts` - The main entry point for the client. This contains the game & Discord SDK configuration which starts the game.
- `packages/client/src/scenes/` - The Phaser Scenes are in this folder.
- `packages/client/public/assets/` - Contains game assets(sprites, sounds, spritesheets, etc).
- `packages/client/src/utils` - Contains custom code for responsivity of the game.
- `packages/server/server.ts` - Contains Discord SDK for OAuth2 & initiates WebSocket server for Colyseus.
- `packages/server/rooms/GameRoom.ts` - Contains game session, channels communication between client/server.
- `packages/server/schemas/GameState.ts` - Defines the structure and types of data that can be synchronized between the server and client.

## Handling Assets

Vite supports loading assets via JavaScript module `import` statements.

This template provides support for both embedding assets and also loading them from a static folder. To embed an asset, you can import it at the top of the JavaScript file you are using it in:

```js
import logoImg from "./assets/logo.png";
```

To load static files such as audio files, videos, etc place them into the `client/assets` folder. Then you can use this path in the Loader calls within Phaser:

```js
preload();
{
  //  This is an example of an imported bundled image.
  //  Remember to import it at the top of this file
  this.load.image("logo", logoImg);

  //  This is an example of loading a static image
  //  from the public/assets folder:
  this.load.image("background", "assets/bg.png");
}
```

When you issue the `npm run build` command, all static assets are automatically copied to the `dist/assets` folder.

## Customizing the Template

### Vite

If you want to customize your build, such as adding plugin (i.e. for loading CSS or fonts), you can modify the `client/vite.config.js` file for cross-project changes, or you can modify and/or create new configuration files and target them in specific npm tasks inside of `package.json`. Please see the [Vite documentation](https://vitejs.dev/) for more information.

## Join the Phaser Community!

We love to see what developers like you create with Phaser! It really motivates us to keep improving. So please join our community and show-off your work 😄

**Visit:** The [Phaser website](https://phaser.io) and follow on [Phaser Twitter](https://twitter.com/phaser_)<br />
**Play:** Some of the amazing games [#madewithphaser](https://twitter.com/search?q=%23madewithphaser&src=typed_query&f=live)<br />
**Learn:** [API Docs](https://newdocs.phaser.io), [Support Forum](https://phaser.discourse.group/) and [StackOverflow](https://stackoverflow.com/questions/tagged/phaser-framework)<br />
**Discord:** Join us on [Discord](https://discord.gg/phaser)<br />
**Code:** 2000+ [Examples](https://labs.phaser.io)<br />
**Read:** The [Phaser World](https://phaser.io/community/newsletter) Newsletter<br />

Created by [Phaser Studio](mailto:support@phaser.io). Powered by coffee, anime, pixels and love.

The Phaser logo and characters are &copy; 2011 - 2024 Phaser Studio Inc.

All rights reserved.
