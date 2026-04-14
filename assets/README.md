# assets/

Drop your images and any small media files here.

## How to upload

1. Go to this folder on GitHub in your browser
2. Click **Add file → Upload files**
3. Drag your images in, scroll down, click **Commit changes**

## How to reference them from `index.html`

Use a relative path:

```html
<img src="assets/my-headshot.jpg" alt="Portrait of me">
<img src="assets/projects/cover-01.png" alt="Project 1 cover">
```

## Rules of thumb

- **Images:** JPG or PNG, keep each file under ~500KB. Resize huge photos before uploading — a 5MB phone photo will make your site feel slow.
- **Video:** **do not** upload video files here. GitHub Pages has a 1GB repo limit and won't stream them well. Upload to YouTube (unlisted works) or Vimeo and embed the link instead — your template has a field for the embed URL.
- **Audio:** same as video — use SoundCloud, Spotify, or Bandcamp embeds, not raw MP3s.
- **Resume PDF:** you can upload it here (e.g. `assets/resume.pdf`) and link to it from the Resume button.

## File naming

Keep filenames lowercase, no spaces. Use `-` instead of spaces.

Good: `fragmented-tides-still-01.jpg`
Bad: `Fragmented Tides Still (1).JPG`
