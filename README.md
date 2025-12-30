AEROVEX SYSTEMS DASHBOARD - DEPLOYMENT GUIDE
=============================================

WHAT YOU HAVE:
- index.html - The complete dashboard
- logo.png - Aerovex logo
- netlify.toml - Netlify configuration
- netlify/functions/chat.js - AI chat backend function

DEPLOYMENT STEPS:
=================

1. CREATE NEW GITHUB REPOSITORY
   - Go to https://github.com/new
   - Name it: aerovex-dashboard (or whatever you want)
   - Set to Public or Private (your choice)
   - DON'T add README, .gitignore, or license (we have files already)
   - Click "Create repository"

2. UPLOAD FILES TO GITHUB
   Option A - Web Interface (Easiest):
   - Click "uploading an existing file"
   - Drag ALL files from this folder
   - Commit directly to main branch
   
   Option B - Git Command Line:
   - Open terminal in this folder
   - Run these commands:
     git init
     git add .
     git commit -m "Initial commit"
     git branch -M main
     git remote add origin https://github.com/YOUR-USERNAME/aerovex-dashboard.git
     git push -u origin main

3. DEPLOY TO NETLIFY
   - Go to https://app.netlify.com
   - Click "Add new site" → "Import an existing project"
   - Choose "Deploy with GitHub"
   - Select your aerovex-dashboard repository
   - Build settings should auto-detect (leave empty)
   - Click "Deploy site"

4. ADD ANTHROPIC API KEY (Required for AI chat)
   - In Netlify, go to Site settings → Environment variables
   - Click "Add a variable"
   - Key: ANTHROPIC_API_KEY
   - Value: [Your Anthropic API key]
   - Click "Save"
   - Trigger a redeploy (Deploys → Trigger deploy → Deploy site)

5. YOUR SITE IS LIVE!
   - Netlify will give you a URL like: https://random-name-123456.netlify.app
   - You can customize the URL in Site settings → Domain management

GOOGLE SHEETS SETUP:
====================
Your dashboard is configured to pull from:

Business Data: 
https://docs.google.com/spreadsheets/d/e/2PACX-1vRIn3pdVIPjOSn7inbbT6FeunwN1RHMLoT3QWkW9-OmzJH9-UTEF3OmOOJYGtXmTxm6K27pf0FE7E9b/pub?gid=1110978664&single=true&output=csv

Ad Campaigns:
https://docs.google.com/spreadsheets/d/e/2PACX-1vRIn3pdVIPjOSn7inbbT6FeunwN1RHMLoT3QWkW9-OmzJH9-UTEF3OmOOJYGtXmTxm6K27pf0FE7E9b/pub?gid=1026635905&single=true&output=csv

To update data:
1. Edit your Google Sheet
2. Changes will appear on dashboard within 1-5 minutes
3. Just refresh the page

TROUBLESHOOTING:
================
- Dashboard not loading? Hard refresh: Ctrl+Shift+R (Windows) or Cmd+Shift+R (Mac)
- Data not updating? Check that "Automatically republish when changes are made" is enabled in Google Sheets
- AI chat not working? Make sure ANTHROPIC_API_KEY is set in Netlify environment variables
- Still having issues? Try Incognito mode to bypass browser cache

FEATURES:
=========
✓ Business Overview - Revenue trends, profit margins, ROAS
✓ Ad Campaign Performance - Meta vs Google comparison  
✓ Revenue Breakdown - Channel analysis and attribution
✓ Monthly Trends - Historical performance tracking
✓ Executive Summary - Key metrics at a glance
✓ AI Chat Assistant - Ask questions about your data
✓ Dark Mode - Toggle in top right
✓ Real-time data from Google Sheets

For support, refer to the original conversation or create a new issue in your GitHub repo.
