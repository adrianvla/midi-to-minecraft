# midi-to-minecraft

## Convert midi files to minecraft .mcfunction.
# How to use:

- convert your midi to json at https://tonejs.github.io/Midi/
- replace the "midi" variable with the json (in the index.html file)  (as an example the midi variable is already a rickroll midi)
- you can map track numbers to minecraft note block instruments (the instruments variable)
- change "songname" to your song's name
- the program will write the contents of the mcfunction file in the browser console (run the index.html file and open your browser's console)

How to start the song in minecraft: 
```
run scoreboard objectives add song_[your_song_name] dummy
scoreboard players set @a song_[your_song_name] 0
```

You also need to run your mcfunction file every tick:
```
# put this in tick.mcfunction

execute if entity @a[scores={song_[your_song_name]=..99999999}] run function path:to/your/generated/file
```
To stop the playback of the song,
```
scoreboard players set @a song_[your_song_name] 100000000
```
