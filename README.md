# scoliosisNET Annotation Tool Static Deploy

This folder is a standalone static website for four-point Cobb annotation.

Files:

```text
index.html
```

It can be deployed to any static website hosting service, such as:

- GitHub Pages
- Cloudflare Pages
- Vercel
- Netlify
- Hospital intranet or public web server

## Important Privacy Note

The page runs in the browser. It does not upload images or JSON to this project by itself.

If you deploy it to a third-party hosting provider, users still open X-ray files locally in their browser and download JSON files locally. They must send the JSON files back to the project team separately.

Do not upload patient-identifiable images or metadata to public repositories or public storage.

## Typical Workflow

1. Upload `index.html` to static hosting.
2. Share the public URL with annotators.
3. Annotators open local de-identified X-ray images.
4. Annotators click four points and download JSON.
5. Collect JSON files and place them in:

```text
datasets/scoliosisNET/annotations/raw
```

6. Convert JSON to YOLO pose labels in the main project.
