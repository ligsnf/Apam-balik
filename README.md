# Wikipedia Page Mirror - Apam Balik

This repository hosts a mirrored version of the Malay Wikipedia page for "Apam balik" via GitHub Pages. The project demonstrates how to create a static mirror of a Wikipedia page while maintaining its styling and functionality.

## Setup Process

### Prerequisites

- WSL 2 (Windows Subsystem for Linux) with Ubuntu
- Basic command line knowledge

### Installation

1. Update package list and install HTTrack:
```bash
sudo apt update
sudo apt install httrack
```

### Downloading the Wikipedia Page

1. Use HTTrack with specific options to download the page:
```bash
httrack "https://ms.wikipedia.org/wiki/Apam_balik" \
  --depth=1 \
  --ext-depth=1 \
  --near
```

Options explained:

* `--depth=1`: Only download the specified page
* `--ext-depth=1`: Follow external links only one level deep
* `--near`: Get files from same directory only

### File Structure Optimization

1. From HTTrack download, copy only the `ms.wikipedia.org` folder initially
2. Move contents from `ms.wikipedia.org` folder to root
3. Move `Apam_balik.html` to root and rename to `index.html`
4. Convert absolute paths to relative paths for GitHub Pages compatibility:
    - `/w/` → `w/`
    - `/static/` → `static/`
5. (Optional) Add necessary external dependency folders (like `creativecommons.org`) as needed for resource references

### Deployment

1. Create a new GitHub repository
2. Initialize local git repository and push to GitHub:
    ```bash
    git init
    git add .
    git commit -m "Initial commit"
    git branch -M main
    git remote add origin <your-repository-url>
    git push -u origin main
    ```
3. Enable GitHub Pages:
    - Go to repository Settings
    - Navigate to Pages section
    - Select 'main' branch as source
    - Save changes

The page will be available at `https://<username>.github.io/<repository-name>/`

## License

Content is subject to Wikipedia's licensing terms.
