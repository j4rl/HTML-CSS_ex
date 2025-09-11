# Links, Images & Multimedia

## Links (Hyperlinks)

### Basic Link Syntax

```html
<a href="https://www.example.com">Visit Example.com</a>
```
- `href` attribute points to the URL.
- Links can be absolute (full URL) or relative (path within your site).

### Useful Link Features & Attributes
- Attribute	Purpose `target="_blank"`	Opens link in a new tab/window
- `rel="noopener noreferrer"`	Improves security/performance when using `target="_blank"`
- `title="..."`	Provides additional info (tooltip), but avoid relying on it as the only description
- `mailto: URI scheme`	Link to send email: `<a href="mailto:someone@example.com">Email us</a>`

### Link Best Practices
- Use meaningful link text that describes destination. Avoid “click here” or “learn more” without context.
- Make sure links are clearly distinguishable (color, underline, hover/focus states).
- For navigation menus, footers, and within content, structure links semantically.

---
## Images
Including an Image
```html
<img src="images/photo.jpg" alt="Description of photo" width="600" height="400">
```

- `alt` attribute: required for accessibility. If image is decorative, use `alt=""`.
- Width & height: helps reserve space and avoid layout shifts.

### Captioned Images
```html
<figure>
  <img src="images/photo.jpg" alt="Snowy mountain landscape">
  <figcaption>Mountain landscape at sunrise</figcaption>
</figure>
```

Use `<figure>` with `<figcaption>` when image needs a caption.

### Responsive Images: srcset / sizes / `<picture>`
```html
<img
  src="images/photo-medium.jpg"
  srcset="
    images/photo-small.jpg 480w,
    images/photo-medium.jpg 800w,
    images/photo-large.jpg 1200w
  "
  sizes="(max-width: 600px) 100vw, (max-width: 1200px) 50vw, 600px"
  alt="A scenic mountain lake at sunset"
  width="1200" height="800"
/>
```

Or use <picture> for format or art-direction:
```html
<picture>
  <source srcset="images/photo.avif" type="image/avif">
  <source srcset="images/photo.webp" type="image/webp">

  <source media="(min-width: 1024px)" srcset="images/photo-large.jpg">
  <source media="(max-width: 1023px)" srcset="images/photo-small.jpg">

  <img src="images/photo-small.jpg" alt="Rolling hills under a colorful sunset" width="800" height="500">
</picture>
```

## Multimedia: Audio & Video
### HTML5 Audio / Video Tags
```html
<audio controls>
  <source src="audio-track.mp3" type="audio/mpeg">
  <source src="audio-track.ogg" type="audio/ogg">
  Your browser does not support the audio element.
</audio>
```
```html
<video controls width="640" height="360">
  <source src="video-HD.mp4" type="video/mp4">
  <source src="video.webm" type="video/webm">
  <track kind="captions" src="captions_en.vtt" srclang="en" label="English">
  Your browser does not support the video element.
</video>
```

- Include multiple source formats so browser picks one it supports.
- Use controls attribute for native controls (play, pause, etc.).
- Provide fallback content inside the tag for browsers that don’t support audio/video.

### Accessibility & Text Alternatives

- Always include captions or subtitles for video. Use `<track>` with `kind="captions"` when available.
- Provide transcript for audio-only or video content with speech.
- Ensure that video player controls are keyboard accessible.

## Other Embedding Techniques

- `<iframe>`: embed another web page (e.g. YouTube video, map). Include title attribute.
- `<embed>` / `<object>`: for PDFs, interactive media, or plugin-content (though usage is more specialized nowadays).

## Best Practices & Accessibility Tips

-Alt text should describe what is important in the image, not decorative details.
- Link text should be context-rich. Example: “Read our privacy policy” rather than “Click here.”
- For video/audio: always ensure that captions or transcript are available.
- Use fallback content for media in case features aren’t supported.
- Ensure multimedia doesn’t autoplay with sound; if autoplay is used, let the user mute/stop it.
