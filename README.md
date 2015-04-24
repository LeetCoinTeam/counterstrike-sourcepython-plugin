# LeetCoin Counter Strike SourcePython Server Plugin
This is a plugin for Counter Strike: Global Offensive and Counter Strike: Source to connect and process data onto the LeetCoin API. To set it up you must have a Counter Strike: GO or Counter Strike: Source server already set up. This has only ever been tested on Linux 32-bit (specifically Ubuntu 14.04 32bit) but it should work on Windows 32-bit as well. 

Once you have your CSGO or CSS server set up you will need to install SourcePython, the middleware we use to connect our plugin to the game servers. You can get the current release of it from their Github over here: 
`https://github.com/Source-Python-Dev-Team/Source.Python/releases/`

To install this you must simply copy all items into their directories on your csgo server files. Below is how we do it when in the sourcepython unzipped directory: 

```
mv addons/ /home/admin/csgoserver/csgo/
cp -R cfg/* /home/admin/csgoserver/csgo/cfg/
mv logs/ /home/admin/csgoserver/csgo/
cp -R resource/* /home/admin/csgoserver/csgo/resource/
cp -R sound/* /home/admin/csgoserver/csgo/sound/
```

> Note: You may also need lib32z1 in certain cases as a dependency. 

Once SourcePython is installed you can start your server and type `sp help` and if the server responds with a list of SourcePython command then you have successfully installed SourcePython. 

The next and final step is to go into your `/csgo/addons/source-python/plugins/` folder and download/clone a copy of our reponsitory onto your machine. To clone it, if you have git installed on your server, you can simply type: 

`git clone https://github.com/LeetCoinTeam/counterstrike-sourcepython-plugin.git`

Once it has downloaded it is best to rename the folder to `leetcoin`. Then you should go into the folder and use your `api_key` and `shared_secret` that you get from us and place them in the spots in leetcoinconfig.py. 

Now if you start your server up again and type the command `sp load leetcoin` and the leetcoin plugin will begin. Congratulations!
