# Race Engineer for F1 26: user guide

Version 1.0

Race Engineer is a Windows app that listens to F1 25 (with the 2026 Season Pack) and talks to you over the radio like a British race engineer: strategy, box calls, gaps, tyres, flags, corner coaching and practice and qualifying programmes. It reads the game's UDP telemetry and plays pre-recorded lines in a cloned voice, so it costs the game almost nothing on the GPU.

Race Engineer is an independent fan project. It is not affiliated with or endorsed by Electronic Arts, Codemasters or Formula 1.

## Contents

1. Requirements
2. Install
3. First run
4. Set up the game
5. What the engineer tells you
6. The window
7. Voices
8. Your data, updates and privacy
9. Troubleshooting
10. Uninstall

## 1. Requirements

- Windows 10 (version 1809 or later) or Windows 11, 64-bit.
- F1 25 with the 2026 Season Pack DLC. The base game's 2025 grid is not supported in 1.0.
- Offline sessions: races, practice and qualifying. Online sessions are not supported.
- About 400 MB of free disk space for the app and its voice, plus room for any extra voices and recordings.
- An internet connection only for the update check and voice downloads. The engineer itself works offline.

No admin rights are needed and .NET is included in the installer.

## 2. Install

1. Download `RaceEngineer-Setup-1.0.0.exe` from the Patreon post or the GitHub releases page.
2. Run it. Windows SmartScreen will probably say "Windows protected your PC", because the installer is not code-signed. Click More info, then Run anyway.
3. Follow the installer. It installs for your Windows user only and can add a desktop icon.
4. Leave "Launch Race Engineer for F1 26" ticked at the end to start it.

To update later, run the new installer over the old one. Your settings, logs, recordings and voices are kept.

## 3. First run

The app opens on the Pit wall page. The status reads "Waiting for the game" until telemetry arrives.

1. Set up the game's telemetry (next section).
2. Press Radio check on the Pit wall. You should hear the engineer. If not, check the volume slider and Windows' output device.
3. Start a session in F1 25. The status changes once the game's data arrives, and the session panel shows the session type and track.

The Setup guide page in the app shows the same steps with pictures.

## 4. Set up the game

F1 25 sends telemetry to one address and port. Choose one of the two setups below.

### Without SimHub

In F1 25, open Settings > Telemetry Settings and set:

| Setting | Value |
|---|---|
| UDP Telemetry | On |
| UDP Broadcast Mode | Off |
| UDP IP Address | 127.0.0.1 |
| UDP Port | 20778 (or the port set in Race Engineer) |
| UDP Send Rate | 60 Hz |
| UDP Format | 2026 |

### With SimHub

SimHub expects the game on port 20777, so leave the game there and let SimHub pass on a copy:

1. In F1 25, set the telemetry as above but with UDP Port 20777.
2. In SimHub, open the F1 25 game settings and add UDP forwarding to `127.0.0.1:20778`.

Both SimHub and Race Engineer then receive the data.

### Changing the port

Race Engineer listens on port 20778 by default. If something else already uses it, pick another port in Settings and send the game (or SimHub's forwarding) to that port instead.

### Game audio

While the engineer speaks, Race Engineer lowers the game's volume in the Windows volume mixer and brings it back afterwards (ducking). Only the game is lowered: your master volume and other apps are not touched. You may also want to turn down the game's own engineer in the F1 25 audio settings so that two engineers do not talk over each other.

## 5. What the engineer tells you

The radio is one-way: the engineer talks, you drive. There is no push-to-talk.

The engineer follows British F1 radio style: short, numbers first, calm, and an instruction at the end of anything that needs one ("Box, box. Box this lap."). Routine calls wait for a straight where they can; urgent calls cut in. On a busy lap the most important calls go first and low-value ones are dropped rather than said late. After a flashback, calls that no longer apply are dropped.

The engineer addresses you by your first name from the game when the voice has that name recorded, otherwise as "mate", and often by nothing at all. You can set how often in Settings.

### Formation lap

Your grid slot and tyres, the track and air temperatures and the weather, a word on the tyres of the cars around you, the race plan, and "line up in your box" in the last sector. If you ran a long run in practice on this track and tyre, the engineer uses it for the tyre life and your first-stint target.

### Strategy and the race plan

The engineer owns a race plan and gives you orders, not options:

- Plan A: one or two stops, the target box laps and the tyre for each stint.
- Plan B: the alternative, for example extending to a later lap or a different tyre.
- Plan C: what we do under a safety car or VSC, and from which lap.

The plan is set on the formation lap, reminded early in each stint, and checked again every lap and after each stop. When it changes you hear the new plan and the reason: tyres wearing faster than expected, an undercut, covering a car behind, a free stop, or traffic at the rejoin. You also hear when the first car on your tyre stops and where you will be once the field has stopped.

The plan uses the game's own tyre data (each set's life and pace) and the pit loss measured from the stops it sees.

### Box calls and the countdown

- A countdown: box in five laps, then in two.
- The order on the box lap: "Box this lap. Box, box," with the tyre.
- One more lap if you would rejoin in traffic, and a reminder if you stay out past the box lap.
- On your out lap: where you are, and your position once everyone has stopped.
- Undercut and overcut chances, the undercut threat from the car behind, and free stops.
- Racing a car at the pit exit.

### Gaps and rivals

- Gaps to the cars ahead and behind, more often in a battle and in the last laps, less in a quiet race.
- The rival's lap time against yours at the line in a close fight.
- Who is catching whom, and in how many laps.
- Sector pace: where a car close to you is quicker or slower, and what to do about it.
- A much faster car coming through ("not our race, let him go"), then who your race is with.
- Rival pit stops and the tyres they took, rival tyre age, and your team-mate's position and pace every few laps.
- Team orders involving your team-mate. These are instructions to you; the AI team-mate cannot be told anything.
- Target lap times to defend or attack, with feedback on the next lap.
- Overtake mode available on the car ahead, and a low battery with a car close behind.
- Position changes, retirements, half distance, laps to go and the final lap.

### Tyres, fuel and damage

- Tyre status from temperatures and lap times: running hot, cold, in the window, going off, and when they are close to the end.
- Fuel saving targets when you are short, and "back on target" when you are not.
- Damage said as its effect and what to do, without percentages, and what it is costing a lap. A front wing gets a box call when a new one pays.
- Punctures, and terminal damage after a heavy crash.

### Flags, safety car and penalties

- Safety car and VSC, with a box or stay out call, safety car in this lap, and VSC ending.
- Red flag and the chequered flag.
- Blue flags in two stages: who is coming to lap you, then "blue flag" when he is close.
- Penalties (time, drive-through, stop-go) and track limits warnings.

### Weather and wet races

Rain on the way, the chance of rain rising, and the track drying, from the game's forecast. In the wet the dry strategy goes quiet and the engineer calls the tyre for the conditions: inters, wets or back to slicks, based on how quick the cars already on them are.

### Corner coaching

When you lose time in the same corner on two clean laps in a row, the engineer says where and how: braking, minimum speed, gear, throttle, or exit speed, with an instruction. When you fix it you hear "that's better".

Coaching needs a map of the track. Race Engineer learns it from your first few clean laps on a track and keeps it, so coaching only starts after that. It stays quiet in a battle, under a safety car or VSC, on lap 1, in the last laps and in qualifying, and says at most one corner a lap. In practice it compares each push lap with your best one and speaks after the push lap, never during it.

### Practice programmes

In practice the engineer runs a programme sized to the time left:

1. Baseline run: a few steady laps. The track map is learned here.
2. Quali sim on the softs: the sign-off before the push lap, then a debrief with your time, position, gap to P1, where you lost time, and whether to go again or box.
3. Long run on the mediums: a target lap, each lap against it, the laps left, and at the end your average, how the pace held and the tyre life.
4. A second long run on the hards when there is time.

Each run is called with its fuel load. A run on the wrong tyre or fuel, or one cut short, is called off with the reason and the plan moves on. Fuel warnings tell you when to box. In the wet there is no programme: the engineer tells you to work on the setup. The results are kept per track and used in qualifying and the race.

### Qualifying

- The start of each segment, with what to expect from your practice pace.
- Out lap: working the tyres, recharging the battery, building a gap to the car ahead.
- The sign-off before the push lap: clear ahead or traffic, the time left to start the lap, battery and tyres, "good to go", or a prep lap when the tyres are cold.
- Traffic: slow cars ahead on your push lap, and cars on a push lap behind you on your out lap.
- Hazards: yellow flags and stopped cars ahead, and "track's clear".
- Abort calls when the lap is invalid or too slow, and what to do next.
- After the push lap: your time and position against the cut or pole, and the plan: cool lap and go again, or box.
- In the garage: when the cut moves, when you drop, and when it is time to go.
- At the flag: whether you are safe, and the result.

Nothing is said during a push lap except traffic and hazards.

### Radio chatter

In quiet stretches the engineer adds the kind of lines real engineers give: strategy modes, engine and brake settings, switch changes and tyre updates. They are for atmosphere and change nothing in the game. There is at most one every few laps, never in a battle.

## 6. The window

The left-hand menu has four pages. The window can be closed at any time; closing it stops the engineer and puts the game's volume back.

### Pit wall

- Status: whether the game is connected, the session, and the voice in use.
- The last call, with Mute engineer, Repeat last call and Radio check.
- Volume.
- The call log for the session. Turn on "Show why each call fired" to see the data behind each call.
- Record: saves the session's telemetry to a recording for replay later.

### Settings

- Voice: the voice in use, voices installed, and more to download.
- Sound: volume and ducking (how far the game is lowered while the engineer speaks).
- Calls: turn groups of calls on or off.
- Name: how often the engineer uses your name.
- Telemetry: the UDP port.
- About and updates: the version and the update check.

### Telemetry and logs

- Recordings, with replay: the engineer talks through a recorded session as if it were live.
- Call logs for each session, with the reason for every call.

Recordings are large, about 45 MB for each minute of racing, so delete the ones you no longer need.

### Setup guide

The game and SimHub setup, step by step with pictures.

### Tray icon

The tray icon stays while the app runs. Right-click it to open the window, mute or unmute the engineer, repeat the last call, or quit.

## 7. Voices

The installer includes one voice, GL Standard. A second voice, JV Calm, downloads from inside the app: Settings > Voice. It is a download of about 27 MB, checked after download. You can switch voices at any time and remove ones you do not use (not the one in use).

The voices are cloned, with their consent, from the voices of real people. They are not the voices of real F1 engineers. Every line is pre-recorded, so there is no live speech generation while you drive.

## 8. Your data, updates and privacy

Everything Race Engineer keeps is in `%AppData%\RaceEngineer`: settings, call logs, recordings, the learned track maps, practice results and the voices.

At start the app checks GitHub for a newer version. If there is one it offers the download page; it never installs anything by itself. Voices are downloaded from the same GitHub releases.

Race Engineer has no account and sends no telemetry, logs or personal data anywhere. The only connections it makes are the update check and voice downloads.

## 9. Troubleshooting

The status stays on "Waiting for the game"

- Check the game's telemetry settings: UDP Telemetry On, UDP Format 2026, IP 127.0.0.1, and the port Race Engineer shows on the Pit wall.
- With SimHub, check that the game sends to 20777 and SimHub forwards to 127.0.0.1:20778, and that SimHub is running.
- If UDP Broadcast Mode is on, turn it off.
- Allow Race Engineer through the Windows firewall if Windows asks.
- Only one program can listen on a port. If another tool uses 20778, change the port in Settings.

The format is wrong

Race Engineer reads UDP Format 2026 only. Format 2025 is not supported.

No sound

- Press Radio check. If you hear nothing, check that the engineer is not muted, the volume slider, and the Windows output device.
- Check the voice in Settings > Voice is installed.

The game does not get quieter when the engineer speaks

Check that ducking is on in Settings. Ducking works on the game's own entry in the Windows volume mixer, so the game must be playing sound.

The engineer is quiet

That is often by design: in a quiet race it says less, it never speaks during a qualifying push lap, and corner coaching needs a few clean laps on a new track first. Check that the call groups you expect are on in Settings. "Show why each call fired" on the Pit wall shows what it is doing.

I started the app mid-race

It picks up lap times, stints and stops from the game's session history. Fuel, wear and pit lane times start from the moment it joined.

The game's volume stayed low

If the app was closed while the engineer spoke, the next start puts the game's volume back once the game is playing sound. You can also reset it in the Windows volume mixer.

A voice download failed

Check your connection and try again. A damaged download is rejected and the old voice stays as it was.

## 10. Uninstall

Open Windows Settings > Apps > Installed apps, find Race Engineer for F1 26 and choose Uninstall. The uninstaller asks whether to remove your data in `%AppData%\RaceEngineer` as well. Choose No to keep your settings, track maps, recordings and voices for a later install.
