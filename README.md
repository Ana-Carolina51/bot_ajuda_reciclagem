import discord
from discord.ext import commands
import random
# Importar pass_gen do bot_logic.py  
from geradorsenha import pass_gen

# A variável intents armazena as permissões do bot
intents = discord.Intents.default()
# Ativar a permissão para ler o conteúdo das mensagens
intents.message_content = True
# Criar um bot e passar as permissões
bot = commands.Bot(command_prefix='$', intents=intents)

@bot.event
async def on_ready():
    print(f'Fizemos login como {bot.user}')

@bot.command()
async def ola(ctx):
    await ctx.send("Ola, tudo bem? Eu sou o Bot Ajuda! Como posso ajudar você hoje? Caso queija ajuda escreva $ajuda")

@bot.command()
async def ajuda(ctx):
    await ctx.send("Aqui estão alguns comandos que você pode usar:\n"
                   "$ola - Cumprimenta o bot\n"
                   "$lixo - Informações sobre lixeiras e reciclagem\n"
                   "$azul - O que jogar na lixeira azul\n"
                   "$vermelho - O que jogar na lixeira vermelha\n"
                   "$verde - O que jogar na lixeira verde\n"
                   "$amarelo - O que jogar na lixeira amarela\n"
                   "$cinza - O que jogar na lixeira cinza\n"
                   "$plastico - Informações sobre decomposição do plástico\n"
                   "$decompor - Informações sobre decomposição de materiais\n"
                   "$reciclagem - Benefícios da reciclagem\n"
                   "$itens - Itens recicláveis e seus usos"
                   "$gif - Envia um gif sobre reciclagem")

@bot.command()
async def lixo(ctx):
    await ctx.send("Cada lixeira joga um tipo de lixo, sabia? Reciclável, orgânico, vidro, metal... Vamos cuidar do nosso planeta! 🌍♻  Digite uma cor e eu te digo oque devemos jogar na lixeira!!️")

@bot.command()
async def azul(ctx):
    await ctx.send("Na lixeira azul, você deve jogar papel e papelão! 📄📰")

@bot.command()
async def vermelho(ctx):
    await ctx.send("Na lixeira vermelha, você deve jogar lixo orgânico! 🍎🥬")

@bot.command()
async def verde(ctx):
    await ctx.send("Na lixeira verde, você deve jogar vidro! 🍾🧴")

@bot.command()
async def amarelo(ctx):
    await ctx.send("Na lixeira amarela, você deve jogar metal! 🛠️🔩")

@bot.command()
async def cinza(ctx):
    await ctx.send("Na lixeira cinza, você deve jogar lixo reciclável!")

@bot.command()
async def plastico(ctx):
    await ctx.send("plásticos comuns levam de 100 a 500 anos, com garrafas PET podendo levar 450-600 anos e fraldas até 450 anos para se decompor. Vamos reciclar! ♻️")

@bot.command()
async def decompor(ctx):
    await ctx.send("Alguns materiais demoram muito para se decompor na natureza. Por exemplo, o alumínio pode levar até 200 anos, enquanto o vidro pode levar até 1 milhão de anos! Vamos cuidar do nosso planeta! 🌍♻️")
                
@bot.command()
async def reciclagem(ctx):
    await ctx.send("Os materiais recicláveis mais comuns são papel, plástico, metal e vidro, que podem ser reaproveitados para criar novos produtos.♻️ Caso queira saber mais digite itens que eu amostro como esses materiais podem ser reciclados!")
                
@bot.command()
async def itens(ctx):
    await ctx.send("Com materiais recicláveis, podemos criar novos produtos, reduzir lixo, poupar energia e recursos naturais, gerar economia e empregos. Digite gif ♻️")

@bot.command()
async def gif(ctx):
    await ctx.send("")

bot.run('')
