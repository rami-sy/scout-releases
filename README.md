# Scout

**العربية** · [English](#english)

Scout تطبيق سطح مكتب يدير صفحاتك على وسائل التواصل بمساعد ذكاء يعمل على جهازك. هذا المستودع فيه ملفات التثبيت والتحديث فقط.

## التنزيل

افتح [آخر إصدار](https://github.com/rami-sy/scout-releases/releases/latest) ونزّل الملف المناسب لجهازك:

| جهازك | الملف | يحدّث نفسه؟ |
|---|---|---|
| Windows 10 أو 11 (64 بت) | `Scout-X-win-x64.exe` | نعم |
| Linux (64 بت)، الأسهل | `Scout-X-linux-x86_64.AppImage` | نعم |
| Ubuntu أو Debian، تثبيت تقليدي | `Scout-X-linux-amd64.deb` | لا، ثبّت كل إصدار يدويًا |

`X` هو رقم الإصدار. أما macOS فغير متاح بعد.

## ما يحتاجه جهازك

- **ذاكرة RAM:** 8 GB على الأقل، والأفضل 16 GB.
- **كرت شاشة:** يسرّع الذكاء كثيرًا، لكنه غير ضروري.
- **مساحة فارغة:** قرابة 10 GB للذكاء.
- **إنترنت:** للتنزيل وللتفعيل، ثم مرة كل 14 يومًا على الأقل ليتحقق Scout من رخصته.
- **مفتاح تفعيل:** تحصل عليه ممن أعطاك Scout، ويعمل على جهاز واحد.

## التثبيت على Windows

1. شغّل `Scout-X-win-x64.exe`.
2. المثبّت غير موقّع بعد، فقد يظهر "Windows protected your PC". اضغط "More info" ثم "Run anyway".
3. اختر مكان التثبيت أو اترك المقترح، ثم أكمل.

## التثبيت على Linux

**AppImage:**

```bash
chmod +x Scout-*.AppImage
./Scout-*.AppImage
```

- **ملف لا يفتح:** AppImage يحتاج مكتبة FUSE 2، ولا تأتي مع Ubuntu 22.04 وما بعده افتراضيًا. ثبّتها مرة واحدة، ثم أعد التشغيل:
  - Ubuntu 24.04 وما بعده: `sudo apt install libfuse2t64`
  - Ubuntu 22.04: `sudo apt install libfuse2`
- **قائمة البرامج:** في أول تشغيل يسألك Scout: "أضيف Scout إلى قائمة البرامج؟". إن وافقت، تجده في القائمة والبحث، لك وحدك وبلا كلمة مرور.
  - احفظ الملف في مكان ثابت، مثل `~/Applications`. التحديثات تستبدله في مكانه، والقائمة تتبعه.
  - إن حذفت الملف، احذف أيضًا `~/.local/share/applications/social-command-center.desktop`.

**deb:**

```bash
sudo apt install ./Scout-*.deb
```

## أول تشغيل

1. **التفعيل:** أدخل مفتاح التفعيل (`SCOUT-XXXXX-XXXXX-XXXXX-XXXXX`). يظهر في النافذة نفسها رمز جهازك، فأرسله إن طلبت المساعدة.
2. **تجهيز الذكاء:** يفحص Scout جهازك ويقترح نموذجًا مناسبًا.
   - إن كان [Ollama](https://ollama.com) مثبتًا عندك، يستعمله Scout ولا ينزّل نسخة ثانية.
   - إن لم يكن مثبتًا، يثبّته بالطريقة الرسمية لنظامك. التنزيل قرابة 8 GB.
   - النماذج تبقى ملكك، وتستطيع استعمالها من الطرفية بـ `ollama`.
3. **إن كان جهازك بطيئًا:** يقترح Scout النموذج الأخف، ويمكنك تخطي الذكاء الآن والعودة إليه من "الإعدادات ← التطبيق ← فتح تجهيز Scout".

## التحديثات

- **AppImage وWindows:** يتحقق Scout من وجود إصدار جديد عند التشغيل، ثم كل 6 ساعات.
  - ينزّل الإصدار الجديد في الخلفية، ويثبّته عند إغلاق Scout، أو فورًا بزر "أعد التشغيل للتحديث".
  - ما تغيّر في كل إصدار تجده في "الإعدادات ← التحديثات والإصدارات".
- **deb:** لا يحدّث نفسه. نزّل الإصدار الجديد وثبّته بالأمر نفسه أعلاه.

## أين تُحفظ بياناتك

كل شيء على جهازك: الصفحات، والمسودات، والذاكرة، والرخصة.

| النظام | مجلد البيانات |
|---|---|
| Windows | `%APPDATA%\social-command-center` |
| Linux | `~/.config/social-command-center` |

نماذج الذكاء في مخزن Ollama العادي (`~/.ollama/models`)، لا داخل Scout.

## الإزالة

- **Windows:** الإعدادات ← التطبيقات ← Scout ← إلغاء التثبيت.
- **AppImage:** احذف الملف.
- **deb:** `sudo apt remove social-command-center`.

الإزالة لا تحذف بياناتك ولا Ollama ونماذجه. احذف مجلد البيانات أعلاه بنفسك إن أردت البدء من جديد.

---

<a id="english"></a>

# Scout (English)

Scout is a desktop app that runs your social pages with an AI assistant on your own computer. This repository holds the installers and update files only.

## Download

Open the [latest release](https://github.com/rami-sy/scout-releases/releases/latest) and download the file for your computer:

| Your computer | File | Updates itself? |
|---|---|---|
| Windows 10 or 11 (64-bit) | `Scout-X-win-x64.exe` | Yes |
| Linux (64-bit), easiest | `Scout-X-linux-x86_64.AppImage` | Yes |
| Ubuntu or Debian, classic install | `Scout-X-linux-amd64.deb` | No, install each version by hand |

`X` is the version number. macOS is not available yet.

## What your computer needs

- **Memory (RAM):** 8 GB at least, 16 GB is better.
- **Graphics card:** makes the AI much faster, but is not required.
- **Free disk space:** about 10 GB for the AI.
- **Internet:** for the download and activation, then at least once every 14 days so Scout can check its license.
- **An activation key:** you get it from whoever gave you Scout. It works on one computer.

## Install on Windows

1. Run `Scout-X-win-x64.exe`.
2. The installer is not signed yet, so you may see "Windows protected your PC". Click "More info", then "Run anyway".
3. Choose where to install, or keep the suggested place, and finish.

## Install on Linux

**AppImage:**

```bash
chmod +x Scout-*.AppImage
./Scout-*.AppImage
```

- **If it does not open:** AppImage needs the FUSE 2 library, which Ubuntu 22.04 and later do not include by default. Install it once, then run Scout again:
  - Ubuntu 24.04 and later: `sudo apt install libfuse2t64`
  - Ubuntu 22.04: `sudo apt install libfuse2`
- **The applications menu:** on first launch Scout asks "Add Scout to your applications menu?". If you agree, you find it in the menu and in search, for you only and without a password.
  - Keep the file in a fixed place, such as `~/Applications`. Updates replace it where it is, and the menu follows.
  - If you delete the file, also delete `~/.local/share/applications/social-command-center.desktop`.

**deb:**

```bash
sudo apt install ./Scout-*.deb
```

## First launch

1. **Activation:** enter your activation key (`SCOUT-XXXXX-XXXXX-XXXXX-XXXXX`). The same window shows your device code; send it along if you ask for help.
2. **AI setup:** Scout checks your computer and suggests a model that fits.
   - If [Ollama](https://ollama.com) is already installed, Scout uses it and never installs a second copy.
   - If it is not installed, Scout installs it the official way for your system. The download is about 8 GB.
   - The models stay yours: you can use them from a terminal with `ollama`.
3. **If your computer is slow:** Scout suggests the lighter model, and you can skip the AI for now and come back to it from "Settings → App → Open Scout setup".

## Updates

- **AppImage and Windows:** Scout checks for a new version at launch, then every 6 hours.
  - It downloads the new version in the background and installs it when you close Scout, or right away with "Restart to update".
  - What changed in each version is under "Settings → Updates and releases".
- **deb:** it does not update itself. Download the new version and install it with the same command as above.

## Where your data lives

Everything stays on your computer: pages, drafts, memory and the license.

| System | Data folder |
|---|---|
| Windows | `%APPDATA%\social-command-center` |
| Linux | `~/.config/social-command-center` |

AI models are kept in Ollama's usual store (`~/.ollama/models`), not inside Scout.

## Uninstall

- **Windows:** Settings → Apps → Scout → Uninstall.
- **AppImage:** delete the file.
- **deb:** `sudo apt remove social-command-center`.

Uninstalling keeps your data, and keeps Ollama and its models. Delete the data folder above yourself if you want a fresh start.
