# ⚡ Quick GitHub Upload - 5 Minutes

**Fast track to uploading your repository**

---

## 🚀 The 5-Step Process

### STEP 1️⃣: Create GitHub Account (2 minutes)

```
1. Go to https://github.com
2. Click "Sign up"
3. Enter email, password, username
4. Verify your email
5. Done! ✅
```

**Your GitHub username will be used in your repository URL:**
```
https://github.com/YOUR_USERNAME/influencerium
```

---

### STEP 2️⃣: Install Git (2 minutes)

**Windows:**
- Download: https://git-scm.com/download/win
- Run installer, click Next → Finish

**macOS:**
```bash
brew install git
```

**Linux:**
```bash
sudo apt-get install git
```

**Verify installation:**
```bash
git --version
```

---

### STEP 3️⃣: Configure Git (1 minute)

Open terminal/command prompt and run:

```bash
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```

Example:
```bash
git config --global user.name "James Ashrof"
git config --global user.email "james@example.com"
```

---

### STEP 4️⃣: Create Repository on GitHub (1 minute)

1. Log in to GitHub
2. Click **+** icon (top right)
3. Select **New repository**
4. Fill in:
   - **Name:** `influencerium`
   - **Description:** Creator-brand collaboration platform
   - **Visibility:** Public or Private
5. Click **Create repository**
6. **Copy the URL** shown (looks like: `https://github.com/yourusername/influencerium.git`)

---

### STEP 5️⃣: Upload Your Code (1 minute)

Open terminal and run these commands:

```bash
# Navigate to your project
cd /workspace

# Add your GitHub repository
git remote add origin https://github.com/YOUR_USERNAME/influencerium.git

# Rename branch to main
git branch -M main

# Push your code to GitHub
git push -u origin main
```

**Replace `YOUR_USERNAME` with your actual GitHub username!**

Example:
```bash
git remote add origin https://github.com/jamesashrof/influencerium.git
git branch -M main
git push -u origin main
```

---

## ✅ Verify It Worked

1. Go to: `https://github.com/YOUR_USERNAME/influencerium`
2. You should see all your files
3. README.md should display
4. Done! 🎉

---

## 🔑 Authentication Help

If prompted for password when pushing:

**Option 1: Use Personal Access Token (Recommended)**

1. Go to GitHub → Settings → Developer settings → Personal access tokens
2. Click "Generate new token"
3. Name: `influencerium`
4. Select: `repo` (full control)
5. Click "Generate token"
6. Copy the token
7. Paste it when prompted for password

**Option 2: Use GitHub CLI**

```bash
gh auth login
# Follow the prompts
```

---

## 🎯 Common Commands Reference

```bash
# Check if Git is configured
git config --global --list

# Check remote repository
git remote -v

# View commit history
git log --oneline

# Check repository status
git status

# Create a new branch
git checkout -b feature/name

# Push a branch
git push -u origin feature/name
```

---

## 📊 What Gets Uploaded

Your repository will contain:

✅ 8 documentation files  
✅ 5 configuration files  
✅ 4 GitHub configuration files  
✅ 3 additional documentation files  
✅ Total: 21 files, ~150KB

---

## 🆘 Troubleshooting

| Problem | Solution |
|---------|----------|
| "fatal: not a git repository" | Make sure you're in `/workspace` directory |
| "Permission denied" | Use Personal Access Token instead of password |
| "Repository already exists" | Run: `git remote remove origin` first |
| "fatal: 'origin' does not appear to be a 'git' repository" | Run: `git remote add origin https://...` |

---

## 🎉 You're Done!

Your repository is now on GitHub!

**Next steps:**
1. Share the URL with your team
2. Integrate docs into your website (see WEBSITE_INTEGRATION_GUIDE.md)
3. Start development
4. Create issues for features

---

**Time to complete:** ~5 minutes  
**Difficulty:** Easy  
**Status:** ✅ Ready to go!
