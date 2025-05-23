HTML Audio (<audio>)

1. Basic Syntax

<audio src="audio.mp3" controls></audio>
Explanation:
<audio> is used to embed audio files in a web page.
It is a media tag like <video>.
By default, audio won't play or show anything unless:
controls is added (for playback controls).
Or it’s controlled by JavaScript.

2. controls Attribute – Display Audio Controls
   Syntax:

<audio src="song.mp3" controls></audio>
Explanation:
Adds built-in playback UI: play, pause, volume, seek, etc.
Without controls, users won’t see a player.
Required unless the audio is meant to be controlled via scripts or autoplay silently.

3. src Attribute – Audio Source (or use <source>)
   Option 1: Inline src

<audio src="sound.mp3" controls></audio>
Option 2: With <source> (for multiple formats)

<audio controls>
  <source src="sound.mp3" type="audio/mpeg">
  <source src="sound.ogg" type="audio/ogg">
  Your browser does not support the audio element.
</audio>
Explanation:
<source> allows you to provide fallback formats.

Helps ensure compatibility across browsers that support different codecs.

4. Audio File Formats
   Format MIME Type Browser Support Notes
   .mp3- audio/mpeg All major Most common
   .ogg- audio/ogg Not in Safari Open format
   .wav- audio/wav All major Large files, no compression
   .aac- audio/aac Most Better quality than MP3
   .flac- audio/flac Firefox/Chrome Lossless
   Best practice: Use .mp3 and optionally .ogg as fallback.

5. Additional Attributes
   autoplay

<audio src="intro.mp3" autoplay></audio>
Audio starts automatically when the page loads.
Often blocked by browsers unless muted or user has interacted with the page.

loop

<audio src="background.mp3" loop controls></audio>
Audio restarts automatically after it ends.

muted

<audio src="alert.mp3" muted autoplay></audio>
Starts audio muted.
Often used in combo with autoplay to allow playback on page load.

preload

<audio src="clip.mp3" controls preload="auto"></audio>
Controls how/when the audio is loaded:
auto: load entire file if possible.
metadata: only load file metadata (duration, size).
none: don’t load until user initiates playback.

id and class
Used to reference the element in CSS or JavaScript:

<audio id="bg-music" src="music.mp3" controls></audio> 6. Accessibility & Fallback
Fallback Content:
<audio controls>

  <source src="file.mp3" type="audio/mpeg">
  Your browser does not support the audio element.
</audio>
Text between <audio> tags is displayed if the browser does not support audio.

Best practices:
Always include meaningful aria-label or title if needed.
Make sure audio doesn’t autoplay without user control (for accessibility and UX).

7. JavaScript Control of Audio
   <audio id="player" src="sound.mp3"></audio>
   <button onclick="document.getElementById('player').play()">Play Sound</button>
   Useful JavaScript Methods:
   Method Purpose
   .play() Starts playback
   .pause() Pauses playback
   .volume = 0.5 Set volume (0 to 1)
   .currentTime = 10 Jump to 10 seconds
   .loop = true Enable looping

8. Common Use Cases
   Background Music (looped, no controls)

<audio src="ambient.mp3" autoplay loop hidden></audio>
Notification Sounds

<audio id="ping" src="ping.mp3"></audio>

<script>
  function notify() {
    document.getElementById("ping").play();
  }
</script>

Language Learning / Audio Clips

<p>Click to hear pronunciation:</p>
<audio id="word" src="hello.mp3"></audio>
<button onclick="document.getElementById('word').play()">🔊 Hear "Hello"</button>
9. Common Mistakes & Fixes
Forgetting controls -Add controls for UI
Audio doesn't play on load- Use autoplay muted or trigger via JS
Missing fallback formats-se <source> tags for compatibility
Audio not accessible-Use aria-label, avoid autoplay

Best Practices
-Use controls unless you’re managing audio with JavaScript.
-Use autoplay muted only when necessary and respectful.
-Include alt text for context near audio content (especially in quizzes, lessons, etc.).
-Optimize audio file size and use efficient formats.
-Respect user settings (e.g. autoplay may frustrate users).
