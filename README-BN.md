# Adnanmarketer — Portfolio Website

একটি responsive personal portfolio website এবং Decap CMS admin panel। Netlify-তে deploy করার জন্য তৈরি।

## ফাইলগুলো
- `index.html`, `styles.css`, `script.js` — ওয়েবসাইট
- `admin/` — CMS admin interface (`/admin/`)
- `content/` — প্রাথমিক profile, service ও project content
- `netlify.toml` — Netlify publish configuration

## Netlify-তে চালু করার ধাপ
1. ZIP extract করুন। পুরো `Adnanmarketer` folder একটি GitHub repository-তে upload করুন। Repository-র branch-এর নাম `main` রাখুন।
2. Netlify-তে লগইন করে **Add new site → Import an existing project** বেছে নিয়ে GitHub repository connect করুন। Build command ফাঁকা রাখুন, publish directory `.` দিন (netlify.toml-এও সেট করা আছে)। Deploy করুন।
3. Netlify site dashboard → **Integrations / Identity** বা **Identity**-তে গিয়ে Netlify Identity enable করুন (যদি আপনার dashboard-এ এই সুবিধা উপলব্ধ থাকে)। Registration বন্ধ করে শুধু নিজের admin account invite করুন।
4. **Identity**-র সঙ্গে **Git Gateway** enable করুন। এই CMS-এর `backend.name: git-gateway` সেই সংযোগ ব্যবহার করে।
5. deploy হওয়া ওয়েবসাইটের `/admin/` খুলুন, নিজের account দিয়ে লগইন করুন। Profile & Site Settings, Services, Portfolio Projects থেকে content সম্পাদনা করুন; ছবি upload করুন; Publish করুন।

> গুরুত্বপূর্ণ: `/admin/` শুধু CMS interface—Git Gateway/Identity ঠিকভাবে configure না করলে publish কাজ করবে না। Netlify account-এ Identity/Git Gateway অপশন না থাকলে Decap CMS-এর বর্তমান supported authentication backend বেছে নিতে হবে। এই starter-এ কোনো password hard-code করা নেই।

## নিজের domain যুক্ত করা
Netlify dashboard → **Domain management → Add a domain** থেকে কেনা domain যোগ করুন। Netlify দেখানো DNS record/domain nameserver আপনার domain registrar-এ বসান। DNS verify ও HTTPS certificate চালু হলে সাইট custom domain-এ চলবে। Domain কেনা বা DNS configure করা এই ZIP-এর বাইরে আলাদা ধাপ।

## আপনার তথ্য দিয়ে কাস্টমাইজ
Admin-এ নিজের profile photo, logo, headline, about, email, social links, service ও project যোগ করুন। `content/settings.json`-এ sample email এবং social URL-গুলো publish করার আগে নিজের সঠিক তথ্য দিয়ে বদলাবেন। Project-এ আপাতত sample placeholder আছে—বাস্তব কাজ/ফলাফল দিয়ে প্রতিস্থাপন করুন।

## সীমাবদ্ধতা
এই সংস্করণটি static portfolio; contact button email app খুলবে, contact submissions কোনো database-এ জমা হয় না। CMS publish করতে GitHub + Netlify CMS backend configuration দরকার।

## বাংলা + English সংস্করণ
- Header-এর `বাংলা` / `English` বাটন দিয়ে ভাষা বদলানো যাবে; পছন্দটি একই ব্রাউজারে মনে রাখা হয়।
- `content/settings.json`-এ `headline1_bn`, `headline2_bn`, `tagline_bn`, `about_bn`, `contact_text_bn` বাংলা কনটেন্টের জন্য আছে।
- `content/services.json`-এ প্রতিটি সার্ভিসের `title_bn` ও `description_bn`; `content/projects.json`-এ `title_bn` ও `category_bn` সম্পাদনা করা যাবে।
- নিজের ইমেইল ও সোশ্যাল লিংক Admin থেকে সেট করুন। যোগাযোগের ইমেইল না দিলে ভুয়া ঠিকানায় পাঠানো হবে না।
