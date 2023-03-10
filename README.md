# zesk.js
Lightweight package for discord.js that supports many cool features
<p align="center">
   <a href="https://www.npmjs.com/package/zesk.js"><img src="https://img.shields.io/npm/v/zesk.js.svg?style=flat-square" /></a>
 <img src="https://nuggies.js.org/assets/img/license.ade17f5e.svg" /></a>
   <br>
   <a href="https://www.npmjs.com/package/zesk.js"><img src="https://nodei.co/npm/zesk.js.png?downloadRank=true&downloads=true&downloadRank=true&stars=true" /></a>
</p>

---
# Features
- [x] Easy to Use
- [x] Lightweight
- Cool Features
  - [x] 📛 Moderation
  - [x] ⭕️ Utility
  - [ ] 🎮 Games and Fun (Will be working)
  - [ ] 🎗 General (Will be working)
---

# Functions
> Confirm Buttons
```js
const { confirmButtons } = require("zesk.js");
const { EmbedBuilder, ButtonStyle } = require("discord.js")
```

```js
await interaction.deferReply();

const embed = new EmbedBuilder()
.setTitle("Some Title")
.setDescription("Some Description")
.setColor("#303136")
// etc

confirmButtons(interaction, {
            embed: embed,
            authorOnly: `Only <@${interaction.member.id}> can use these buttons`,
            yes: {
                style: ButtonStyle.Primary,
                label: "Yes",
                emoji: "✔️",
            },
            no: {
                style: ButtonStyle.Secondary,
                label: "No",
                emoji: "🛑",
            },
        }).then(async (confirm) => {
            if (confirm === "yes") {
                interaction.editReply({
                    content: `Content to show when pressed yes`,
                });
            if (confirm === "no") {
                interaction.editReply({
                    content: `Content to show when pressed no`,
                });
            }
            if (confirm === "time") {
                interaction.editReply({
                    content: `Time up content`,
                });
            }
        });
```

more examples at example directory.
