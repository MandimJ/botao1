import discord
import random

TOKEN = "OTMzNDk2MDU4NzgzMzM4NjI5.YeiX8w.nK3FC6XsD3jSFw1tL1Kcluw2mi8"

client = discord.Client()


def get_quote():
    response = requests.get
    ("https://zenquotes.io/api/random")
    json_data = json.loads(response.text)
    quote = json_data[0]['q'] + " -" + json_data[0]["a"]
    return (quote)


@client.event
async def on_ready():
    print(f'{client.user} seu ganda boi!')


@client.event
async def on_message(message):
    username = str(message.author).split("#")[0]
    user_message = str(message.content)
    channel = str(message.channel.name)
    print(f'{username}: {user_message} ({channel})')

    if message.author == client.user:
        return
    if message.content.startswith('mekie'):
        await message.channel.send(f'Mekie Boi!')
        return
    elif user_message.lower() == 'ta tudo?':
        await message.channel.send(f'Ta tudo primaço!')
        return

    if message.content.startswith('Seu bot'):
        await message.channel.send(f'Bot és tu cabecao kkkk!')
        return
    elif user_message.lower() == 'Pash':
        await message.channel.send(f'Ai pash kkkk!')
        return


client.run(TOKEN)
