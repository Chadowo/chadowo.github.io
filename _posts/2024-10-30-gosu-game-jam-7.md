---
layout: post
author: Chadow
title: "Gosu Game Jam 7: The Humans Are Rebelling!"
tags: [programming, videogames]
---

![finished game screenshot](assets/images/media/thar_screenshot.png)

I made a [game](https://chadow.itch.io/the-humans-are-rebelling) for the [7th Gosu Jam](https://itch.io/jam/gosu-game-jam-7). Here‘s a little analysis about the good and the bad.

## What Went Right

### 1. Graphics

Thankfully I managed to create some simple graphics for the game, otherwise it would‘ve been boring.

### 2. Levels

My first time making any sorts of level into a game. The levels (called *rooms* in my code) are loaded by the class `Room`. They are represented in a simple text file, that looks like this:

```
# This is the start room of every run.

1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,
1,1,1,1,1,1,1,1,1,1,0,0,0,0,0,0,0,0,0,0,0,1,1,1,1,1,1,
1,1,1,1,1,1,1,1,1,1,0,0,0,0,0,0,0,0,0,0,0,1,1,1,1,1,1,
1,0,0,1,0,0,0,0,0,1,0,0,0,0,0,0,0,0,0,0,0,1,1,1,1,1,1,
1,0,0,1,0,0,@,0,0,1,0,0,1,0,0,0,0,0,0,0,0,0,0,0,0,1,1,
1,0,0,1,1,0,0,0,1,1,0,0,1,0,0,0,0,0,0,0,0,0,0,0,0,0,0,
1,0,0,0,0,0,0,0,0,0,0,0,1,0,0,1,1,0,0,0,0,0,0,0,0,0,0,
1,0,0,0,0,0,0,0,0,0,0,0,1,0,0,1,1,0,0,0,0,0,0,0,0,0,0,
1,0,0,0,0,1,1,1,0,0,0,0,1,0,0,1,1,0,0,0,0,0,0,0,0,0,0,
1,0,0,0,0,1,1,1,0,0,0,0,1,0,0,0,0,0,0,0,0,0,0,0,0,0,0,
1,0,0,0,0,0,0,0,0,0,0,0,1,0,0,0,0,0,0,0,0,0,0,0,0,1,1,
1,0,0,0,0,0,0,0,0,0,0,0,0,0,0,1,1,0,0,0,0,1,1,1,1,1,1,
1,0,0,0,0,0,0,0,0,0,0,0,0,0,0,1,1,0,0,0,0,1,1,1,1,1,1,
1,0,0,0,0,0,0,0,0,0,0,0,0,0,0,1,1,0,0,0,0,1,1,1,1,1,1,
1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,
```

It looks quite intimidating, but it‘s far more stupid and simple that‘d you think:

- `0`: represents an empty space.
- `1`: represents a wall.
- `@`: is the spawn point of the player.
- `#`: used for comments.

In the future, I would like to integrate [Tiled](https://www.mapeditor.org/) to make more complex stuff.

## What Went Wrong

### 1. Uncreative Design

I‘m quite bad, and I mean *bad* bad at coming up with game ideas. And even if I come up with something, it must be doable, something small ‘n simple. In the end I decided to recreate an old game that loosely fits the theme.

### 2. AI

I can‘t stress how *badly* the AI in this game is. It would be correct to say they‘re more like obstacles than a bot or anything. The following pseudo-code should give you an idea of how they‘re implemented:

```ruby
# Movement
move(random_direction, random_distance) every 1..5 seconds

# Shooting
if player_in_rect_line and can_shoot then shoot!
```

This means that the humans are highly likely to suicide by going against the walls since they have no concept of avoiding the walls whatsoever. They also have no idea of how to pursue the player.

### 3. Architecture

The game layout‘s all over the place. I‘d benefit a lot from organizing a little bit more.

### 4. Crunching

This is on me really. Initially I wanted to develop most of the game when the jam started, however one way or another I just managed to set up the boilerplate code and the real development only started like 6 days into the jam. In the final day I had to crunch some 8 hours to develop graphics, “AI”, collisions and exporting. Plus the game‘s finicky structure made it easy to get bugs.

## Closing Thoughts

All in all, I‘m just content with having a (kinda) working game. Good experience but really tiring ☆⌒(> _ <). And to think there are people that can [make a game in one hour](https://onehourgamejam.com/)…

On the following weeks, I‘m planning to correct some of the things that went wrong with the game, and uploading it on GitHub. Of course under an open-source license.
