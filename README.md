# AudioPlayerView

A polished, drop-in audio player screen for SwiftUI — artwork, title, scrubber, transport controls, volume, and AirPlay, all wired up to a single view.

Built on `AVPlayer` and `MediaPlayer`, it also handles the system integrations you'd otherwise write by hand: Now Playing info on the lock screen and in Control Center, plus remote transport controls (play/pause, skip, and scrubbing from the lock screen).

## Features

- 🎨 **Full player UI** — artwork, title/subtitle, seek bar with elapsed/remaining time, play/pause with a springy bounce, ±30s skip buttons
- 🎚 **Interactive scrubbing** — drag the seeker with frame-accurate seeking and live time labels
- 🔊 **Volume slider** and **AirPlay picker** built in
- 🔒 **Lock screen & Control Center support** — Now Playing metadata (title, artist, artwork, duration, elapsed time) stays in sync automatically
- 🎧 **Remote commands** — play, pause, skip forward/back 30s, and scrub-to-position all work from the lock screen, Control Center, and headphones
- 📡 **Streams remote audio** — just pass a URL

## Requirements

- iOS 15+
- Swift 5.8+

## Installation

Add the package in Xcode (**File → Add Package Dependencies…**) using:

```
https://github.com/benjaminsage/AudioPlayerView.git
```

Or add it to your `Package.swift`:

```swift
dependencies: [
    .package(url: "https://github.com/benjaminsage/AudioPlayerView.git", branch: "main")
]
```

## Usage

```swift
import SwiftUI
import AudioPlayerView

struct PlayerScreen: View {
    var body: some View {
        AudioPlayerView(
            url: URL(string: "https://example.com/episode.mp3"),
            title: "Episode 42",
            subtitle: "My Favorite Podcast",
            image: UIImage(named: "artwork")!
        )
    }
}
```

That's it — playback, seeking, volume, AirPlay, and lock-screen controls are all handled for you.

### Background audio

To keep audio playing when the app is backgrounded, enable the **Audio, AirPlay, and Picture in Picture** background mode in your target's *Signing & Capabilities* tab. The package configures the `AVAudioSession` playback category for you.

## License

MIT
