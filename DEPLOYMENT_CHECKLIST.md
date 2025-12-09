# 🚀 Quick Deployment Checklist

Use this as a quick reference while following the full deployment guide.

## ☑️ Pre-Deployment Checklist

- [ ] Git installed and repository pushed to GitHub
- [ ] MongoDB Atlas account created
- [ ] Render.com account created
- [ ] All code changes committed and pushed

## 🗄️ MongoDB Atlas Setup

- [ ] Create free M0 cluster
- [ ] Create database user (save username & password)
- [ ] Allow access from anywhere (0.0.0.0/0)
- [ ] Get connection string and save it

**Connection String Format:**
```
mongodb+srv://USERNAME:PASSWORD@cluster0.xxxxx.mongodb.net/starshield?retryWrites=true&w=majority
```

## 🔧 Backend Deployment (Render)

- [ ] Create new Web Service
- [ ] Connect GitHub repository
- [ ] Configure service:
  - Build Command: `npm install`
  - Start Command: `node server.js`
- [ ] Add environment variables:
  - `NODE_ENV` = `production`
  - `MONGODB_URI` = (your connection string)
  - `JWT_SECRET` = (random secret string)
  - `PORT` = `8080`
- [ ] Deploy and save backend URL

## 🎨 Frontend Deployment (Render)

### Option 1: Separate Static Site (Recommended for Learning)
- [ ] Update `.env.production` with backend URL
- [ ] Commit and push changes
- [ ] Create new Static Site
- [ ] Configure:
  - Build Command: `npm install && npm run build`
  - Publish Directory: `build`
- [ ] Add environment variable:
  - `REACT_APP_API_URL` = (your backend URL)
- [ ] Deploy

### Option 2: Single Service (Simpler)
- [ ] Just deploy backend (it serves the frontend automatically)
- [ ] No separate frontend deployment needed!

## ✅ Post-Deployment

- [ ] Test Sign Up functionality
- [ ] Test Sign In functionality
- [ ] Test adding a website
- [ ] Check MongoDB Atlas for data
- [ ] Set up UptimeRobot (optional, keeps app awake)

## 📝 Important URLs

| Service | URL |
|---------|-----|
| MongoDB Atlas | https://cloud.mongodb.com |
| Render Dashboard | https://dashboard.render.com |
| Backend URL | _________________________ |
| Frontend URL | _________________________ |
| GitHub Repo | _________________________ |

## 🔄 To Update Your App

```bash
git add .
git commit -m "Your changes"
git push origin main
```

Render auto-deploys! 🎉

## 🆘 Common Issues

**Backend won't start:**
- Check environment variables in Render
- Verify MongoDB connection string

**Frontend can't connect:**
- Check `REACT_APP_API_URL` is set correctly
- Verify backend is running

**Database errors:**
- Check MongoDB Atlas IP whitelist
- Verify username/password in connection string

---

**Need detailed instructions?** See the full [DEPLOYMENT_GUIDE.md](./DEPLOYMENT_GUIDE.md)
