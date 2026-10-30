# TIGER AI — Android APK Build Project

यह Android app project है। इसमें TIGER का black/red interface, Hindi speech-to-text (Android SpeechRecognizer), और बोलकर जवाब (Android TextToSpeech) जोड़ा गया है।

## अभी क्या काम करता है
- Android app के अंदर TIGER interface
- Microphone permission लेकर Hindi voice input (जब app खुला हो)
- Hindi/English में बोले गए जवाब
- Basic local time/date/greeting commands
- वैकल्पिक secure AI backend URL

## अभी क्या शामिल नहीं है
- यह ZIP स्वयं APK नहीं है; APK को Android build runner पर compile करना होगा।
- Background/locked-screen “Hey Tiger” wake word नहीं है।
- केवल आपकी आवाज़ पहचानने/voice biometric lock की सुविधा नहीं है।
- Full AI के लिए अलग secure backend और API key चाहिए। API key APK में न डालें।

## मोबाइल से APK बनाने का आसान तरीका (GitHub Actions)
1. ZIP को फोन में डाउनलोड करके extract करें।
2. GitHub पर नया repository बनाएं: https://github.com/new
3. Extract किए गए project के अंदर की सभी files/folders repository में upload करें। `.github/workflows/build-apk.yml` भी upload होना चाहिए।
4. GitHub repository में **Actions** खोलें → **Build TIGER APK** चुनें → **Run workflow** दबाएं।
5. Build पूरा होने पर उसी workflow run के नीचे **Artifacts** में `TIGER-debug-APK` डाउनलोड करें।
6. ZIP artifact खोलें; `app-debug.apk` फोन में install करें। Android पूछे तो Chrome/Files के लिए “Install unknown apps” अनुमति दें।

## Build requirements
- Android Gradle Plugin 8.6.1
- Gradle 8.7
- JDK 17
- compile SDK 35

## सुरक्षा
Microphone केवल app खुला होने पर, user के tap और Android permission के बाद इस्तेमाल होता है। API secret कभी भी app source या APK में न रखें।
