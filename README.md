# Rollio Kitchen — Website

Landing page for Rollio Kitchen premium silicone kitchen essentials.

## Deploy to Railway

1. Push this repo to GitHub
2. Go to [railway.app](https://railway.app) → **New Project** → **Deploy from GitHub repo**
3. Select this repository — Railway will auto-detect the `Dockerfile`
4. Your site will be live at the generated Railway URL in ~2 minutes

## Deploy to AWS

### Option A — AWS Amplify (simplest)
1. Go to **AWS Amplify Console** → **New App** → **Host web app**
2. Connect your GitHub repo
3. Amplify will serve `index.html` directly as a static site

### Option B — S3 + CloudFront
```bash
# Create bucket
aws s3 mb s3://rollio-kitchen-site

# Enable static hosting
aws s3 website s3://rollio-kitchen-site --index-document index.html

# Upload
aws s3 cp index.html s3://rollio-kitchen-site/ --acl public-read
```

### Option C — Docker (ECS / App Runner)
```bash
docker build -t rollio-kitchen .
docker run -p 80:80 rollio-kitchen
```

## Images

All images are sourced from [Unsplash](https://unsplash.com) under the free Unsplash License, which permits commercial use with no attribution required.
