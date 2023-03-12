```js
const { confirmButtons } = require("zeck.js");
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
