# Assets

This directory contains the project's visual assets.

## File description

| File | Usage | Dimensions |
|------|------|------|
| `logo.svg` | Project Logo | 200x200 |
| `banner.svg` | README Top Banner | 1200x300 |
| `social-preview.html` | GitHub Social Preview Template | 1280x640 |

## Generate Social Preview image

GitHub's Social Preview requires PNG/JPG format. Generate using:

### Method 1: Browser screenshot

1. Open `social-preview.html` with a browser
2. Use developer tools to adjust the window size to 1280x640
3. Save the screenshot as `social-preview.png`

### Method 2: Command line tools

```bash
# Use Playwright
npx playwright screenshot social-preview.html social-preview.png --viewport-size=1280,640

# Or use Puppeteer
npx capture-website social-preview.html --width=1280 --height=640 --output=social-preview.png
```

### Method 3: Online Tools

1. Access [Carbon](https://carbon.now.sh/) or [Ray.so](https://ray.so/)
2. Custom design
3. Export as image

## Set up GitHub Social Preview

1. Open the repository Settings
2. Click on the "Social preview" area
3. Upload `social-preview.png`
4. Save

## Customize

All SVG files can be modified with a text editor. Primary color variant:

```
Main color: #667eea (blue-violet)
Secondary color: #764ba2 (purple)
Accent color: #f093fb (pink)
Highlight color: #f5576c (reddish pink)
Background color: #0f0c29, #302b63, #24243e (dark gradient)
```
