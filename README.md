# Action-Bot
For discord
import discord
from discord.ext import commands
import random

# Replace 'YOUR_BOT_TOKEN' with your actual bot token
TOKEN = 'YOUR_BOT_TOKEN'

intents = discord.Intents.default()
intents.message_content = True  # Required for message content
bot = commands.Bot(command_prefix='!', intents=intents)

@bot.event
async def on_ready():
    print(f'Logged in as {bot.user.name}')
    print(f'Bot ID: {bot.user.id}')
    print('------')
    await bot.change_presence(activity=discord.Game(name="Doing Actions!"))

@bot.command(name='hug')
async def hug(ctx, target: discord.Member = None):
    """Hugs a specified user or the bot itself."""
    hug_gifs = [
        "https://media.giphy.com/media/vCKC987U5iJwfwxqGh/giphy.gif",
        "https://media.giphy.com/media/l4KieSaHXcOGtevoI/giphy.gif",
        "https://media.giphy.com/media/U8iiB9GBdt5t9n1I6J/giphy.gif",
        "https://media.giphy.com/media/qscdhWs5o3yb6/giphy.gif",
        "https://media.giphy.com/media/BXrwTdoRcLleO9NsJ9/giphy.gif",
    ]
    hug_gif = random.choice(hug_gifs)

    if target:
        await ctx.send(f'{ctx.author.mention} hugs {target.mention}! {hug_gif}')
    else:
        await ctx.send(f'{ctx.author.mention} hugs themselves! {hug_gif}')

@bot.command(name='pat')
async def pat(ctx, target: discord.Member = None):
    """Pats a specified user or the bot itself."""
    pat_gifs = [
        "https://media.giphy.com/media/109ltuoSQ2KP56/giphy.gif",
        "https://media.giphy.com/media/3oEduVpgi9W784zHeg/giphy.gif",
        "https://media.giphy.com/media/10UeedrT5MIfPG/giphy.gif",
        "https://media.giphy.com/media/l41YfykEff9Y9xji0/giphy.gif",
        "https://media.giphy.com/media/5OqX9b9BGrrvIdrzS0/giphy.gif",
    ]
    pat_gif = random.choice(pat_gifs)

    if target:
        await ctx.send(f'{ctx.author.mention} pats {target.mention}! {pat_gif}')
    else:
        await ctx.send(f'{ctx.author.mention} pats themselves! {pat_gif}')

@bot.command(name='wave')
async def wave(ctx, target: discord.Member = None):
    """Waves at a specified user or the bot itself."""
    wave_gifs = [
        "https://media.giphy.com/media/YjGz5RV9hC3Nu/giphy.gif",
        "https://media.giphy.com/media/l3q2K5jinAlChoCLS/giphy.gif",
        "https://media.giphy.com/media/Y6H9Tf6mBqLhK/giphy.gif",
        "https://media.giphy.com/media/l0MYH8jY3s5j0i66s/giphy.gif",
        "https://media.giphy.com/media/l41Yc36vj8936J71u/giphy.gif",
    ]
    wave_gif = random.choice(wave_gifs)

    if target:
        await ctx.send(f'{ctx.author.mention} waves at {target.mention}! {wave_gif}')
    else:
        await ctx.send(f'{ctx.author.mention} waves at themselves! {wave_gif}')

@bot.command(name='slap')
async def slap(ctx, target: discord.Member = None):
    """Slaps a specified user. Use with caution!"""
    slap_gifs = [
        "https://media.giphy.com/media/jLeyZWjYtZqfu/giphy.gif",
        "https://media.giphy.com/media/jhcYhH6w9HjMI/giphy.gif",
        "https://media.giphy.com/media/gGnQHSbE827j2/giphy.gif",
        "https://media.giphy.com/media/ZqWMXgD7371eE/giphy.gif",
        "https://media.giphy.com/media/Y6H9Tf6mBqLhK/giphy.gif"
    ]
    slap_gif = random.choice(slap_gifs)

    if target:
        await ctx.send(f'{ctx.author.mention} slaps {target.mention}! {slap_gif}')
    else:
        await ctx.send(f'{ctx.author.mention} slaps themselves! {slap_gif}')

@bot.command(name='poke')
async def poke(ctx, target: discord.Member = None):
    poke_gifs = [
        "https://media.giphy.com/media/10FHR5A46bfL3O/giphy.gif",
        "https://media.giphy.com/media/3o7TKyOb3vV6c9xXjG/giphy.gif",
        "https://media.giphy.com/media/l41YkAP9M9mXh1l6g/giphy.gif",
        "https://media.giphy.com/media/l41YxX2QYm3j32YyQ/giphy.gif",
        "https://media.giphy.com/media/l41YyR76n7c8y26iQ/giphy.gif",
    ]
    poke_gif = random.choice(poke_gifs)
    if target:
        await ctx.send(f'{ctx.author.mention} pokes {target.mention}! {poke_gif}')
    else:
        await ctx.send(f'{ctx.author.mention} pokes themselves! {poke_gif}')

bot.run(TOKEN)

