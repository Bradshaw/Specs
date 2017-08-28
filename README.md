# Specifications

Rotonde is a self-hosted, platform and programming language agnostic social media experiment. Its purpose is simply to share feeds of daily activity logs between its members. See [this feed](http://rotonde.xxiivv.com) for an example.

You may browse [the custom clients](https://github.com/Rotonde) for inspiration.

## Answer
### The JSON structure for the Rotonde API. 

The answer is the minimum required structure for the data answered by rotonde calls.

```
{
  "profile":
  {
    "name":"Devine Lu Linvega",
    "location":"Huahine",
    "origin": "rotonde.xxiivv.com",
    "position":"-16.812254, -150.989524",
    "color":"#72dec2",
    "glyph": "M240,240 l0,-90 a-90,-90 0 0,0 -90,-90 l-90,0 l0,90 a90,90 0 0,0 90,90 l60,0 l0,-90 a-60,-60 0 0,0 -60,-60 l-60,0 l0,60 a60,60 0 0,0 60,60 l30,0 l0,-60 a-30,-30 0 0,0 -30,-30 l-30,0 l0,30 a30,30 0 0,0 30,30",
    "avatar":"http://wiki.xxiivv.com/public.oscean/media/brand/logo.devine.lu.linvega.png",
    "topics": ["audio", "visual", "research", "update"]
  },
  "feed":[
    {
      "id":4,
      "time":"1497499200",
      "text":"Worked on Rotonde specs.",
      "topic":"Rotonde",
      "task":"Development",
      "data":
      {
        "focus":0.5,
        "sleep":0.3
      }
    },
    {
      "id":3,
      "time":"1496326400",
      "media":"http://wiki.xxiivv.com/public.oscean/media/diary/339.jpg",
      "text":"Worked on the Rotonde specs.",
      "topic": "research",
      "url":"http://xxiivv.com/index.htm",
      "data":
      {
        "focus":0.6,
        "sleep":0.6,
        "nutrition":0.7
      }
    }
  ],
  "dialog":[
    {
      "time":"1497499200",
      "ref":"rotonde.monochromatic.co 1497326400",
      "text":"!kudo"
    },{
      "time":"1497499200",
      "ref":"rotonde.cblgh.org 1577326300",
      "type":"Very nice, thank you."
    }
  ],
  "portal":
  [
    "rotonde.cblgh.org",
    "rotonde.monochromatic.co",
    "rotonde.brennan.pizza/feed.json",
    "rotonde.anxl.faith",
    "rotonde.electricgecko.de",
    "rotonde.attilam.com"
  ]
}
```

### Profile
Profile information.
#### Name
Your display name.
#### Location
Current location.
#### Origin
The origin of your portal.
#### Position
Current geoposition in decimal, not degree-hour.
#### Color
Hex value for display highlights.
#### Avatar*
A url to an image.
#### Glyph*
A single SVG path stroke data, created on a canvas of 300x300.
#### Topics*
An array of strings to organize entries by.

### Feed
Array of Entries, recommended limit of 30.
#### Time
Unixtime.
#### Media
Url to attached image, audio, video.
#### Ref
Url of distant rotonde instance, followed by unixtime.
#### Text
Text content of the entry.
#### Url
Attached URL of the entry.
#### Position
The entry's geoposition in decimal, not degree-hour.
#### Topic
The entry's topic. One per entry.

### Feed > Data
Feed data in the format of a string key, and a float value.
#### Focus(Example)
Float between 0 and 1, of the day's available time dedicated to task.
#### Nutrition(Example)
Float between 0 and 1, of the daily nutritional goal.
#### Sleep(Example)
Float between 0 and 1, of the daily sleep time goal.
#### Exercise(Example)
Float between 0 and 1, of the daily exercise goal.

### Portal
Array of subscribed rotonde instance urls, recommended limit of 30.
