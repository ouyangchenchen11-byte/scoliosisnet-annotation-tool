# Deploy scoliosisNET Annotation Tool Online

Goal: make the annotation tool accessible from the public internet even when the development computer is shut down.

This requires static website hosting. The tool is a single static HTML file:

```text
index.html
```

It does not require Python, Node, a database, or the scoliosisNET training project to run online.

## Recommended Option: GitHub Pages

1. Create a GitHub account or use an existing one.
2. Create a new public repository, for example:

```text
scoliosisnet-annotation-tool
```

3. Upload this file to the repository root:

```text
dist/scoliosisnet-annotation-tool/index.html
```

4. In GitHub, open:

```text
Settings -> Pages
```

5. Set:

```text
Source: Deploy from a branch
Branch: main
Folder: /root
```

6. Save.

After a short wait, GitHub will provide a URL like:

```text
https://YOUR_USERNAME.github.io/scoliosisnet-annotation-tool/
```

That URL will work from any computer on the internet, even when this local computer is off.

## Alternative: Cloudflare Pages

1. Create or log into a Cloudflare account.
2. Go to:

```text
Workers & Pages -> Create -> Pages
```

3. Choose direct upload.
4. Upload:

```text
dist/scoliosisnet-annotation-tool.zip
```

5. Cloudflare will provide a URL like:

```text
https://PROJECT_NAME.pages.dev
```

## Privacy Notes

- Do not upload patient X-ray images to a public repository.
- The online annotation page runs in the browser.
- Users select local image files on their own computer.
- JSON files are downloaded locally by each annotator.
- The project team still needs to collect JSON files and place them in:

```text
datasets/scoliosisNET/annotations/raw
```

## What This Does Not Do

This online static site does not automatically save annotations to your computer or server. If you need central upload and account management, that requires a backend server and storage design.
