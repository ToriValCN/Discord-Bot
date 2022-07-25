import os
import discord
import random

my_secret = os.environ['token2.0']

client = discord.Client()

sad_thoughts = [
    'depressed', 'depressing', 'sad', 'crine', 'upset', 'grades', 'hard',
    'school', 'pharm', 'exams', 'finals', 'bad day'
]

encouraging_words = [
    'ur so smart bestie <3', 'I BEELIEVE IN UUUUU', 'YOURE THE BESTEST',
   'you can do it!',
    'if there were no failures, successes wouldnt matter!'
]
fun_words = ['smart', 'cute', 'sweet', 'funny', 'awesome', 'genius', 'cool', 'adorable', 'CUTE']
#encouraging_emojis = ['\U0001F929', '\U0001F607']

hydration_words = [
    'drink', 'water', 'thirsty', 'lyann.', 'hydrate', 'hydration'
]

starter_hydration = [
    'lyann. drink water NOW ', 'HYDRATION STATION', 'Hydrate or Die-drate',
    'u need water neeowwwwwww'
]


@client.event
async def on_ready():
    print('{0.user} is online! '.format(client))

@client.event
async def on_message(message):
    username = str(message.author).split('#')[0]
    user_message = str(message.content)
    channel = str(message.channel.name)
    print(f'{username}: {user_message} ({channel})')

    if message.author == client.user:
        return

    msg = message.content
  
    if message.content == 'sad':
        await message.add_reaction('\U0001F62D')
    elif any(word in msg for word in fun_words):
        await message.add_reaction('\U0001F929')
        await message.add_reaction('\U0001F496')

    if any(word in msg for word in hydration_words):
        await message.channel.send(random.choice(starter_hydration))
        return
    elif any(word in msg for word in sad_thoughts):
        await message.channel.send(random.choice(encouraging_words))
        return

    if user_message.lower() == 'hello':
        response = f'Hello {username}'
        await message.channel.send(response)
        return
    elif user_message.lower() == 'bye':
        response = f'See ya {username}'
        await message.channel.send(response)
        return
    elif user_message.lower() == 'drink':
        response = f'This is your sign to hydrate @{username}'
        await message.channel.send(response)
        return
    elif user_message.lower() == 'are u proud':
        response = f'Yeah are you???'
        await message.channel.send(response)
        return
    elif user_message.lower() == 'good bot':
        response = f'awww thank u uwu'
        await message.channel.send(response)
        return
    elif user_message.lower() == 'lion needs water':
        response = f'LYANN DRINK WATER'
        await message.channel.send(response)
        return
    elif user_message.lower() == 'lyann.':
        response = f'HYDRATE CHECK!'
        await message.add_reaction('\U0001F62D')
        await message.channel.send(response)
        return
    elif user_message.lower() == 'no':
        response = f'YES!'
        await message.channel.send(response)
        return
    elif user_message.lower() == 'bad bot':
        response = f'im sowwy uwu i twy my bwest'
        await message.channel.send(response)
        return

client.run(os.getenv('token2.0'))
