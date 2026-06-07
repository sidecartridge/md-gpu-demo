# md-gpu-demo

`md-gpu-demo` is a demoscene-oriented showcase built on top of
[`md-framebuffer-template`](https://github.com/sidecartridge/md-framebuffer-template).
It demonstrates what can be done when a SidecarTridge Multi-device
cartridge, also known as **SidecarT**, works together with an Atari ST,
STE, Mega ST, or Mega STE.

The repository is not just a static framebuffer sample. It is a small
intro/demo playground where the RP2040 in the SidecarT renders effects
into a 320x200 chunky framebuffer, while the Atari side receives
tear-free 50 Hz updates, keyboard input, palette changes, and YM audio.

## What It Shows

The demo set focuses on classic Atari and demoscene building blocks:

- **Animated boot menu** with a rotozooming SidecarTridge backdrop,
  palette beating, keyboard navigation, and timing readouts.
- **Uridium-style parallax** with layered starfields, metal grids,
  transparent scrolling surfaces, and a controllable ship.
- **Filled 3D vector object** using fixed-point rotation, projection,
  backface culling, triangle filling, and shaded Atari ST palettes.
- **Multi-sprite stress demo** adapted from a Pico VGA demo, showing many
  animated sprites, transparent blits, and frame-budget tracking.
- **Cojorotozoom intro effect** with fixed-point rotozoom, bitmap
  scroll-text, palette ramps, transparent texture sampling, and sprite
  overlays.

The point is to explore the overlap between the SidecarT's RP2040 compute
budget and the visual style of ST-era intros: rotozoomers, scrollers,
sprite swarms, parallax, palette tricks, and vector objects running on
real Atari hardware.

## Relationship To md-framebuffer-template

This repo is based on
[`md-framebuffer-template`](https://github.com/sidecartridge/md-framebuffer-template).
For implementation details, build instructions, and the underlying
framebuffer framework, use that project as the reference.

## Platform

Supported Atari targets:

- Atari ST
- Atari STE
- Atari Mega ST
- Atari Mega STE

Hardware: SidecarTridge Multi-device / SidecarT.

## Controls

From the menu:

- `Up` / `Down`: move the menu selection
- `Return`: launch the selected demo
- `1` / `2` / `3` / `4`: launch a demo directly
- `D`: toggle the DRAW/C2P timing readout
- `Esc`: exit back to GEM

Inside a demo:

- `Esc`: return to the menu
- `D`: toggle timing readouts

Some demos use additional cursor-key controls, such as the parallax
ship demo's vertical movement.

## Returning To Booster

[Booster](https://docs.sidecartridge.com/) is the SidecarT
configurator app used to install, update, and switch microfirmware
apps. There are two ways back to it:

- **Hold the cartridge SELECT button while powering on / resetting the
  Atari.** This is a hardware escape hatch: it jumps straight to Booster
  before this app's configuration or emulation runs, so you can always
  reach the configurator even if the app's settings are wrong or it
  misbehaves.
- **Reflash / power-cycle normally** once Booster has been told to load a
  different app.

Pressing `Esc` only exits the running demo back to GEM (the Atari
desktop); it does **not** return to Booster.

## License

GPL v3.0. See [LICENSE](LICENSE).
