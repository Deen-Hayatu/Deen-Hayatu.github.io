# Image Optimization Guide

## Current Image Sizes
- profile.jpg: 109KB
- RG.jpg: 27KB  
- linkedin.png: 726 bytes
- X.png: 3.4KB

## Optimization Steps

### Option 1: Online Tools (Easiest)
1. **TinyPNG** (https://tinypng.com/)
   - Upload profile.jpg and RG.jpg
   - Download optimized versions
   - Replace original files

2. **Squoosh** (https://squoosh.app/)
   - Convert to WebP format (better compression)
   - Adjust quality to 80-85%
   - Download and save as profile.webp

### Option 2: Using Node.js (Automated)
Install sharp package:
```bash
npm install sharp
```

Create optimize-images.js:
```javascript
const sharp = require('sharp');
const fs = require('fs');
const path = require('path');

const imagesToOptimize = [
  { input: 'profile.jpg', quality: 85 },
  { input: 'RG.jpg', quality: 90 }
];

imagesToOptimize.forEach(({ input, quality }) => {
  const inputPath = path.join(__dirname, input);
  const outputPath = path.join(__dirname, input.replace('.jpg', '-optimized.jpg'));
  const webpPath = path.join(__dirname, input.replace('.jpg', '.webp'));

  // Optimize JPEG
  sharp(inputPath)
    .jpeg({ quality, progressive: true })
    .toFile(outputPath);

  // Create WebP version
  sharp(inputPath)
    .webp({ quality })
    .toFile(webpPath);
});
```

Run: `node optimize-images.js`

### Option 3: Use ImageMagick
```bash
# Install ImageMagick first
magick convert profile.jpg -quality 85 -strip profile-optimized.jpg
magick convert profile.jpg -quality 85 profile.webp
```

## Expected Results
- profile.jpg: 109KB → ~40-60KB (JPEG) or ~30-40KB (WebP)
- RG.jpg: 27KB → ~15-20KB
- Total savings: ~50-60KB (faster load time)

## Implementation
After optimization, update index.html to use WebP with JPEG fallback:
```html
<picture>
  <source srcset="assets/images/profile.webp" type="image/webp">
  <img src="assets/images/profile.jpg" alt="..." />
</picture>
```
