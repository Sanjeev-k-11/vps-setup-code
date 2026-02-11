# 🚀 Optimized Git Full Code Update Guide (Goride)

## 1. Project Directory & Hard Reset (Safer than Pull)
```bash
cd ~/Goride
 git fetch --all && git reset --hard origin/main
```

## 2. Backend Update & Zero-Downtime Reload

```bash
# npm ci fast aur reliable hai production ke liye
npm ci --production
# reload se application bina down hue update ho jati hai
pm2 reload all
```

## 3. Frontend Rebuild

```bash
cd frontend
# Clean install dependencies
npm ci
# Build production files
npm run build

```

## 4. Nginx Safe Reload

```bash
 sudo nginx -t && sudo systemctl reload nginx
```

 ## ✅ 5. Health Check
 ```bash
git status
pm2 status
sudo systemctl status nginx
```

