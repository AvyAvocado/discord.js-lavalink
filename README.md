# discord.js-lavalink
A lavalink client for Discord.js with queue support which is just a single Array + other changes


## Things to consider
If you really want to use this thing you should this things on your code:
- `<PlayerManager>` receives `vchannel` instead of `channel` but also `tchannel` which is used to annouce things about the Player
```javascript
const player = await client.player.join({
    guild: message.guild.id,
    vchannel: message.member.voiceChannelID,
    tchannel: message.channel.id,
    host: client.player.nodes.first().host
  });
```
- `<Player>` needs the whole song instead of the track's Base64 string
```javascript
{
  track: 'QAAA1gIAbOOAkOadseaWueODnOODvOOCq+ODq+OAkSDjgIzjgr/jgqTjg4vjg7zjg6rjg4jjg6vjg7vjgqLjgrjjgqLjg7Pjgr/jg6DjgI0g44CQU2hpYmF5YW5SZWNvcmRz44CRIOOAkFN1YmJlZOOAkQAQQWxpY2UgTWFyZ2F0cm9pZAAAAAAABWbQAAtTbUtLRzZ0Q1AzTQABACtodHRwczovL3d3dy55b3V0dWJlLmNvbS93YXRjaD92PVNtS0tHNnRDUDNNAAd5b3V0dWJlAAAAAAAAAAA=',
  info: {
    identifier: 'SmKKG6tCP3M',
    isSeekable: true,
    author: 'Alice Margatroid',
    length: 354000,
    isStream: false,
    position: 0,
    title: '【東方ボーカル】 「タイニーリトル・アジアンタム」 【ShibayanRecords】 【Subbed】',
    uri: 'https://www.youtube.com/watch?v=SmKKG6tCP3M',
    requester: '『 』#5212'
  }
}
```
- `<Player>` now looks like this
```javascript
Player {
  _events: [Object: null prototype] {
    error: [ [Function], [Function] ],
    end: [Function: bound onceWrapper] {
      listener: [AsyncFunction (anonymous)]
    }
  },
  _eventsCount: 2,
  _maxListeners: undefined,
  id: '607740801853947904',
  vchannel: '607740801853947908',
  tchannel: '652253810592448523',
  queue: [],
  requester: '『 』#5212',
  playing: true,
  paused: false,
  state: { volume: 100, position: 85100, time: 1581112496628 },
  track: 'QAAA1gIAbOOAkOadseaWueODnOODvOOCq+ODq+OAkSDjgIzjgr/jgqTjg4vjg7zjg6rjg4jjg6vjg7vjgqLjgrjjgqLjg7Pjgr/jg6DjgI0g44CQU2hpYmF5YW5SZWNvcmRz44CRIOOAkFN1YmJlZOOAkQAQQWxpY2UgTWFyZ2F0cm9pZAAAAAAABWbQAAtTbUtLRzZ0Q1AzTQABACtodHRwczovL3d3dy55b3V0dWJlLmNvbS93YXRjaD92PVNtS0tHNnRDUDNNAAd5b3V0dWJlAAAAAAAAAAA=',
  timestamp: 1581112410932
}
```


## Documentation
[**https://github.com/MrJacz/discord.js-lavalink**](https://github.com/MrJacz/discord.js-lavalink/)


~~For a proper example look at [**example/app.js**](https://github.com/MrJacz/discord.js-lavalink/blob/master/example/app.js)~~ this thing doesn´t work because i did some changes
