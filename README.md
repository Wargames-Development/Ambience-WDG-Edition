<!-- Update links and badges as public release pages become available -->
<!-- [![Curse Forge](https://cdn.jsdelivr.net/npm/@intergrav/devins-badges@3/assets/cozy/available/curseforge_vector.svg)]() -->
<!-- [![Modrinth](https://cdn.jsdelivr.net/npm/@intergrav/devins-badges@3/assets/cozy/available/modrinth_vector.svg)]() -->

<!-- [![Patreon](https://cdn.jsdelivr.net/npm/@intergrav/devins-badges@3/assets/cozy/donate/patreon-plural_vector.svg)](https://www.patreon.com/c/WargamesMc) -->
[![Discord](https://cdn.jsdelivr.net/npm/@intergrav/devins-badges@3/assets/cozy/social/discord-plural_vector.svg)](https://discord.wargames.uk)

# Ambience WDG Edition

Ambience WDG Edition is the Wargames Development Group-maintained 1.7.10 fork of Ambience, focused on stable custom soundtrack playback for multiplayer modpacks.

This project is based on the original Ambience mod by Vazkii and is being maintained specifically for Wargames use-cases, compatibility, and long-term reliability on legacy 1.7.10 environments.

The goal of this fork is to preserve the mod’s lightweight event-based music system while cleaning up crash points, modernizing the build and release flow, and retaining the useful soundtrack-event improvements that were relied on previously.

Please check out our [Credits Section](#meet-our-team--credits) for the people behind the project.

<br>

<!-- Replace this with a proper Ambience WDG banner once produced -->
<!-- ![Ambience WDG Edition Banner](https://github.com/Wargames-Development/<repo>/blob/main/assets/Ambience-WDG-Banner.png?raw=true) -->

## What is Ambience WDG Edition?

Ambience WDG Edition is a client-side soundtrack controller for Minecraft 1.7.10 that allows custom music to play dynamically based on world conditions and configured events.

It is intended to provide:

- event-based custom soundtrack playback
- configurable music selection through properties files
- support for multiple tracks per event
- shuffled event track selection
- compatibility with legacy 1.7.10 client environments
- safer audio handling on systems with inconsistent JavaSound mixer support

Unlike the original archived release, this fork is being maintained with direct focus on practical use in real modpacks rather than remaining frozen in its older public state.

## Current Direction

This fork is intentionally being kept small and focused.

The main goals are:

- preserve Ambience’s existing music-event functionality
- retain the useful multi-track shuffle behavior previously used from the Soundtrack Events fork
- fix client crashes caused by unsupported JavaSound gain controls
- standardize build output, versioning, and repository structure with other WDG Edition mods
- keep the mod simple to build and maintain for 1.7.10

## Planned / Active Fixes

The immediate maintenance targets for this fork are:

- fix `Unsupported control type: Master Gain` client crashes
- harden audio gain handling so unsupported mixers do not crash the client
- preserve shuffled event soundtrack support from the previously used fork
- preserve comma-separated multi-song event configuration support
- review and keep the music slider behavior working correctly
- keep the mod client-safe and lightweight without dragging in unnecessary external complexity

## Configuration Overview

Ambience WDG Edition uses the same general Ambience-style configuration approach:

- place music files in the expected client music folder
- define event mappings in the properties configuration
- optionally provide multiple songs for an event separated by commas
- allow the mod to randomly choose between configured songs for that event

Example concept:

```properties
event.night=night1,night2,night3
event.generic=overworld1,overworld2
```

This allows each event to pull from a small pool of suitable tracks instead of always replaying the same song.

## Documentation

### Documentation Coming Soon

More detailed setup documentation, event lists, and example configurations can be added here later if the fork grows beyond its current maintenance scope.

For now, this repository should be treated primarily as the source of truth for the maintained WDG build.

<br>

---

## Support Us!

Are you enjoying our work?
Consider supporting development!

The **Wargames Development Group** is building a wider ecosystem around our projects, including server infrastructure, mod development, and hosting support through Wargames Hosting.

Instead of treating donations as the main focus, we want long-term support to eventually come through the wider Wargames platform and hosting services as they release.

Until then, support through Patreon helps us continue funding development, testing, and maintenance work tied to projects like this one.

[![Patreon](https://cdn.jsdelivr.net/npm/@intergrav/devins-badges@3/assets/cozy/donate/patreon-plural_vector.svg)](https://www.patreon.com/c/WargamesMc)

## Need to get in touch?

Our main place for community discussion, support, and announcements is our [Discord Server](https://discord.wargames.uk).

Feel free to send an email to:
- `dev@wargames.uk` for development-related concerns
- `abuse@wargames.uk` for serious abuse or security-related matters

Please note that email is not intended to replace community support for normal mod questions. For general help, bug reports, or feedback, please use the Discord server.

---

## Compiling the Current Version

If releases are behind the current source progress and you want to test the latest code, you can compile the current version yourself.

Please keep in mind that the repository may contain work-in-progress maintenance changes depending on what has recently been patched.

<details>
<summary>View Detailed Steps:</summary>

1. Enter the source code directory
    1. Navigate to the location where you downloaded the sources.
    2. Enter the downloaded source tree.
    3. On Windows 11, Shift + Right-Click and select `Open in terminal`.

       If this opens PowerShell and you would rather use Command Prompt:

        1. Open a CMD window manually
        2. Change into the project directory:

       ```cmd
       cd /path/to/project-root/dir/
       ```

<br>

2. Build the mod
    1. Run:

   ```cmd
   gradlew build
   ```

    2. Wait for completion

<br>

3. Locate the mod file
    1. Enter the project directory.
    2. Navigate to `build/libs`.
    3. Grab the produced `.jar` file.

</details>

## Contributing

Anyone is welcome to contribute and help improve the project.

That said, this fork is intended to stay small, focused, and maintainable. Contributions should avoid turning it into a bloated rewrite and should instead preserve the original scope of the mod while improving stability and maintainability.

A few important principles:

- keep fixes surgical
- preserve expected Ambience behavior unless a change is clearly intentional
- prioritize client stability
- avoid unnecessary dependency growth
- keep legacy 1.7.10 compatibility intact
- document any behavior changes that affect configuration or playback logic

<details>
<summary>View Detailed Steps:</summary>

1. Follow the compilation steps above first.

2. Setup the decomp workspace
    1. Type `gradlew setupDecompWorkspace` and then click enter
    2. Wait for completion

3. Depending on your editor of choice follow one of the below:

* Intellij Idea:
    1. Generate idea files by running `gradlew idea` in the terminal.
    2. Open the generated project in IntelliJ IDEA.

* Eclipse Users:
    1. Generate eclipse files by running `gradlew eclipse` in the terminal.

</details>

---

## Meet our Team / Credits

### Original Mod
- Vazkii — original Ambience mod author

### Included Library Credits
- JavaZoom / JLayer — bundled MP3 playback library used by Ambience

### Wargames Development Group Maintenance
- Wargames Development Group — maintained WDG Edition fork, build modernization, stability fixes, and soundtrack-event feature preservation
