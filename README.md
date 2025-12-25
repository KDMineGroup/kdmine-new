# 🏗️ Kavian Development Mine - Complete Website Package

## 📋 Overview

This is a complete, production-ready website for **Kavian Development Mine** (کاویان توسعه معدن), specializing in mining equipment engineering and economics.

### ✨ Key Features

- ✅ **No Backend Required** - Uses EmailJS for email notifications
- ✅ **Bilingual Support** - Persian (B-Nazanin) & English (Times New Roman)
- ✅ **Fully Responsive** - Mobile, Tablet, Desktop optimized
- ✅ **Admin Dashboard** - Manage registrations and contacts
- ✅ **Email Notifications** - Automatic emails for all actions
- ✅ **LocalStorage Database** - No server database needed initially
- ✅ **Professional Design** - Modern, clean, and optimized

---

## 📦 Package Contents

```
kdmine.com/
├── index.html                      # Homepage (Bilingual)
├── register.html                   # User Registration
├── contact.html                    # Contact Form
├── about.html                      # About Us
├── portfolio.html                  # Portfolio/Case Studies
├── services.html                   # Services Overview
├── technical-resources.html        # Technical Resources Hub
├── services/
│   ├── equipment-selection.html
│   ├── concentration-plants.html
│   ├── leaching-systems.html
│   ├── acid-production.html
│   ├── technology-optimization.html
│   ├── vendor-partnerships.html
│   ├── economic-analysis.html
│   └── risk-analysis.html
├── admin/
│   ├── login.html                  # Admin Login
│   └── dashboard.html              # Admin Dashboard
└── README.md                       # This file
```

---

## 🚀 Quick Start (5 Minutes)

### Step 1: Setup EmailJS (Free Account)

1. **Create Account**
   - Go to https://www.emailjs.com/
   - Sign up (Free: 200 emails/month)
   - Verify your email

2. **Add Email Service**
   - Dashboard → **Email Services** → **Add New Service**
   - Choose **Gmail** (recommended)
   - Follow connection steps
   - **Copy your Service ID** (e.g., `service_abc123`)

3. **Create Email Templates**

   Create these 4 templates in EmailJS:

   #### Template 1: Registration Request (to Admin)
   - **Template ID**: `template_registration`
   - **Template Name**: "New Registration Request"
   - **Subject**: `درخواست عضویت جدید از {{from_name}}`
   - **Content**:
   ```
   درخواست عضویت جدید دریافت شد:
   
   نام: {{from_name}}
   ایمیل: {{user_email}}
   تلفن: {{phone}}
   شرکت: {{company}}
   سمت: {{position}}
   حوزه تخصصی: {{expertise}}
   سطح دسترسی: {{access_level}}
   
   توضیحات:
   {{message}}
   
   لطفاً به پنل مدیریت مراجعه کنید:
   https://www.kdmine.com/admin/dashboard.html
   ```

   #### Template 2: Registration Confirmation (to User)
   - **Template ID**: `template_confirmation`
   - **Template Name**: "Registration Confirmation"
   - **Subject**: `تایید دریافت درخواست - کاویان توسعه معدن`
   - **Content**:
   ```
   سلام {{from_name}} عزیز،
   
   درخواست عضویت شما با موفقیت دریافت شد.
   
   درخواست شما در حال بررسی است و پس از تایید، اطلاعات ورود به سیستم برای شما ارسال خواهد شد.
   
   این فرآیند معمولاً 24-48 ساعت زمان می‌برد.
   
   با تشکر،
   تیم کاویان توسعه معدن
   www.kdmine.com
   info@kdmine.com
   ```

   #### Template 3: Contact Form Submission
   - **Template ID**: `template_contact`
   - **Template Name**: "Contact Form"
   - **Subject**: `پیام جدید از {{from_name}}`
   - **Content**:
   ```
   پیام جدید از فرم تماس:
   
   نام: {{from_name}}
   ایمیل: {{user_email}}
   تلفن: {{phone}}
   موضوع: {{subject}}
   
   پیام:
   {{message}}
   
   ---
   ارسال شده از: www.kdmine.com
   ```

   #### Template 4: Approval Notification (to User)
   - **Template ID**: `template_approval`
   - **Template Name**: "Account Approved"
   - **Subject**: `تایید عضویت - کاویان توسعه معدن`
   - **Content**:
   ```
   سلام {{from_name}} عزیز،
   
   درخواست عضویت شما تایید شد! 🎉
   
   اطلاعات ورود شما:
   ━━━━━━━━━━━━━━━━━━━━
   نام کاربری: {{username}}
   رمز عبور: {{password}}
   سطح دسترسی: {{access_level}}
   ━━━━━━━━━━━━━━━━━━━━
   
   برای ورود به سیستم از لینک زیر استفاده کنید:
   https://www.kdmine.com/technical-login.html
   
   توصیه می‌کنیم پس از اولین ورود، رمز عبور خود را تغییر دهید.
   
   با تشکر،
   تیم کاویان توسعه معدن
   www.kdmine.com
   ```

4. **Get Your Credentials**
   - Dashboard → **Account** → **General**
   - **Copy your Public Key** (e.g., `YOUR_PUBLIC_KEY`)

### Step 2: Update Configuration

Replace these values in **ALL HTML files**:

```javascript
// Find and replace in:
// - index.html
// - register.html
// - contact.html
// - admin/dashboard.html

emailjs.init("YOUR_PUBLIC_KEY");           // Replace with your Public Key
const SERVICE_ID = "YOUR_SERVICE_ID";      // Replace with your Service ID
const TEMPLATE_REGISTRATION = "template_registration";
const TEMPLATE_CONFIRMATION = "template_confirmation";
const TEMPLATE_CONTACT = "template_contact";
const TEMPLATE_APPROVAL = "template_approval";
```

**Quick Find & Replace:**
- `YOUR_PUBLIC_KEY` → Your actual EmailJS Public Key
- `YOUR_SERVICE_ID` → Your actual EmailJS Service ID
- `admin@kdmine.com` → Your actual admin email
- `info@kdmine.com` → Your actual info email

### Step 3: Update Admin Credentials

In `admin/login.html`, change default credentials:

```javascript
// Line ~150
const ADMIN_USERNAME = 'admin';           // Change this
const ADMIN_PASSWORD = 'Admin@2025';      // Change this
```

### Step 4: Upload to Server

Upload all files to your web hosting:

```bash
# Via FTP/SFTP
- Upload entire folder structure
- Maintain directory hierarchy
- Set proper permissions (755 for directories, 644 for files)
```

### Step 5: Test Everything

1. **Test Homepage**: Visit `https://www.kdmine.com/`
2. **Test Registration**: Fill form at `/register.html`
3. **Check Email**: Verify you received admin notification
4. **Test Admin Login**: Go to `/admin/login.html`
5. **Approve User**: Login and approve the test registration
6. **Check Approval Email**: Verify user received credentials
7. **Test Contact Form**: Submit a contact message

---

## 🔧 Configuration Details

### EmailJS Settings

| Setting | Value | Location |
|---------|-------|----------|
| Public Key | `YOUR_PUBLIC_KEY` | All HTML files |
| Service ID | `YOUR_SERVICE_ID` | All HTML files |
| Registration Template | `template_registration` | register.html |
| Confirmation Template | `template_confirmation` | register.html |
| Contact Template | `template_contact` | contact.html |
| Approval Template | `template_approval` | admin/dashboard.html |

### Admin Credentials

| Field | Default Value | Change In |
|-------|---------------|-----------|
| Username | `admin` | admin/login.html |
| Password | `Admin@2025` | admin/login.html |

### Email Addresses

| Purpose | Default | Change In |
|---------|---------|-----------|
| Admin Email | `admin@kdmine.com` | All template parameters |
| Info Email | `info@kdmine.com` | Footer sections |
| Support Email | `support@kdmine.com` | Contact page |

---

## 📊 How It Works

### User Registration Flow

```
1. User fills registration form
   ↓
2. EmailJS sends notification to admin
   ↓
3. EmailJS sends confirmation to user
   ↓
4. Data stored in localStorage
   ↓
5. Admin reviews in dashboard
   ↓
6. Admin approves with credentials
   ↓
7. EmailJS sends login info to user
   ↓
8. User can now login
```

### Contact Form Flow

```
1. User submits contact form
   ↓
2. EmailJS sends message to admin
   ↓
3. Data stored in localStorage
   ↓
4. Admin views in dashboard
   ↓
5. Admin marks as read
```

### Admin Dashboard Features

- ✅ View all pending registrations
- ✅ Approve/reject users
- ✅ Generate credentials automatically
- ✅ Send approval emails
- ✅ View contact messages
- ✅ View approved users
- ✅ Filter by status/access level
- ✅ Real-time statistics

---

## 🎨 Customization

### Change Colors

Edit CSS variables in each HTML file:

```css
:root {
    --primary: #1e3a8a;      /* Main blue */
    --secondary: #2563eb;    /* Light blue */
    --accent: #3b82f6;       /* Accent blue */
    --success: #059669;      /* Green */
    /* ... */
}
```

### Change Fonts

Current fonts:
- **Persian**: B-Nazanin (system font)
- **English**: Times New Roman

To use custom fonts, add `@font-face` rules or link to Google Fonts.

### Add New Services

1. Create new HTML file in `/services/` folder
2. Copy structure from `equipment-selection.html`
3. Update content
4. Add link in homepage services grid
5. Add link in footer

---

## 📱 Responsive Breakpoints

| Device | Breakpoint | Layout |
|--------|------------|--------|
| Mobile | < 768px | Single column |
| Tablet | 768px - 1024px | 2 columns |
| Desktop | > 1024px | 3-4 columns |

---

## 🔐 Security Notes

### Current Implementation (LocalStorage)

⚠️ **Important**: This version uses localStorage for data storage, which is:
- ✅ Perfect for testing and small-scale use
- ✅ No server setup required
- ❌ Data stored in browser only
- ❌ Not suitable for production with multiple admins
- ❌ Data can be cleared by user

### Recommendations for Production

1. **Change Admin Password** immediately
2. **Use HTTPS** for your domain
3. **Backup localStorage** data regularly
4. **Migrate to Backend** when you have:
   - Multiple admins
   - More than 50 users
   - Need for data persistence
   - Payment integration

### Future Migration Path

When ready to scale:

```
Current: HTML + EmailJS + LocalStorage
   ↓
Phase 1: Add PHP backend + MySQL
   ↓
Phase 2: Add payment gateway
   ↓
Phase 3: Add advanced features
```

---

## 🐛 Troubleshooting

### Emails Not Sending

**Problem**: EmailJS not working

**Solutions**:
1. Check Public Key is correct
2. Check Service ID is correct
3. Check Template IDs match exactly
4. Check EmailJS account is verified
5. Check free tier limit (200 emails/month)
6. Check browser console for errors

### Admin Can't Login

**Problem**: Invalid credentials

**Solutions**:
1. Check username/password in `admin/login.html`
2. Clear browser cache
3. Check for typos
4. Try incognito mode

### Data Not Saving

**Problem**: LocalStorage not working

**Solutions**:
1. Check browser supports localStorage
2. Check browser not in private mode
3. Check localStorage not full (5-10MB limit)
4. Clear localStorage and try again

### Fonts Not Loading

**Problem**: B-Nazanin not displaying

**Solutions**:
1. Install B-Nazanin font on system
2. Or add web font version
3. Fallback to Tahoma works fine

---

## 📈 Analytics Integration

### Add Google Analytics

Add before `</head>` in all HTML files:

```html
<!-- Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=GA_MEASUREMENT_ID"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'GA_MEASUREMENT_ID');
</script>
```

---

## 🚀 Performance Optimization

Already implemented:
- ✅ Minimal external dependencies
- ✅ Optimized CSS (no framework bloat)
- ✅ Font display swap
- ✅ Lazy loading ready
- ✅ Compressed animations
- ✅ Efficient selectors

---

## 📞 Support

For issues or questions:
- **Email**: info@kdmine.com
- **Website**: www.kdmine.com

---

## 📝 License

© 2025 Kavian Development Mine. All rights reserved.

---

## ✅ Checklist Before Going Live

- [ ] EmailJS account created and verified
- [ ] All 4 email templates created
- [ ] Public Key updated in all files
- [ ] Service ID updated in all files
- [ ] Admin credentials changed
- [ ] Admin email updated
- [ ] Test registration completed
- [ ] Test approval email received
- [ ] Test contact form working
- [ ] Admin dashboard accessible
- [ ] All links working
- [ ] Mobile responsive checked
- [ ] HTTPS enabled
- [ ] Domain configured
- [ ] Analytics added (optional)
- [ ] Backup plan in place

---

## 🎉 You're Ready!

Your website is now ready to deploy. Upload the files and start receiving registrations!

**Need help?** Contact us at info@kdmine.com
