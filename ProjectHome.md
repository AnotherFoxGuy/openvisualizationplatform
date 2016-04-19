OpenVP is a free and open-source platform for developing music visualizations, written in C# and developed primarily on Linux.  The Tao Framework OpenGL bindings are used for effect rendering.

The high-level goal of OpenVP is to develop a platform-neutral, media-player-neutral framework for developing music visualizations.  The framework should impose as few restrictions on creativity as possible while also providing a base that makes this flexibility easy to consume.

The core framework is suitable for:

  * Embedding into another application.
  * Extending by creating new standalone effects.
  * Extending by creating new presets that react to specific songs in specific ways.

In particular, the mechanism used to obtain PCM and frequency spectrum data (as well as song metadata like title and current playback position) is left up to the embedding application in the form of an abstract base class.  Further support is available for providing custom beat detection systems to the framework.

The GTK+ user interface in the project can, in its current form, be used to rapidly create new visualization presets and to test new effects.  It uses the reflection capabilities of the CLI to discover new effect types and generate property sheets with little developer effort.  Eventually it will turn into a complete visualization studio, allowing the development of presets containing keybindings and custom switchboards, and hopefully time-scripted visualization.

Some of the core effects use a custom compiler written specifically for this project to allow users to alter the behavior of effects without requiring them to create new effect assemblies.  The casual user may be able to pick up on a simple scripting language quickly but is unlikely to know C# or even have a development environment handy.  Eventually I would like to move away from this custom compiler to something a bit more standardized, but no compiler currently exists for the CLR that is capable of generating garbage-collectible methods.