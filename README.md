# Revolt.py

[![GitHub Repo stars](https://img.shields.io/github/stars/revoltchat/revolt.py)](https://github.com/revoltchat/revolt.py/stargazers) ![PyPI - Python Version](https://img.shields.io/pypi/pyversions/revolt.py) ![PyPI - Status](https://img.shields.io/pypi/status/revolt.py) ![GitHub issues](https://img.shields.io/github/issues/revoltchat/revolt.py) ![GitHub pull requests](https://img.shields.io/github/issues-pr/revoltchat/revolt.py)

An async library to interact with the https://revolt.chat API. This library will **only support bots** and I will **not** implement anything exclusively for user accounts.

You can join the support server [here](https://rvlt.gg/FDXER6hr) and find the library's documentation [here](https://revoltpy.readthedocs.io/en/latest/). 

## Installing

You can use `pip` to install revolt.py. It differs slightly depending on what OS/Distro you use.

On Windows and some Linux distros (where Python 3.X is called with `python`)
```
python3 -m pip install -U revolt.py # -U to update
```

On macOS and some Linux distros (where Pythob 3.X is called with `python3`)
```
python3 -m pip3 install -U revolt.py
```

## Example

More examples can be found in the [examples folder](https://github.com/revoltchat/revolt.py/blob/master/examples).

```py
import revolt
import asyncio
import aiohttp

class Client(revolt.Client):
    async def on_message(self, message: revolt.Message):
        if message.content == "hello":
            await message.channel.send("hi how are you")

async def main():
    async with aiohttp.ClientSession() as session:
        client = Client(session, "BOT TOKEN HERE")
        await client.start()

asyncio.run(main())
```
