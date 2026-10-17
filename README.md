# Passio 안드로이드 앱

열톡(/talk)을 앱으로 띄우는 껍데기(TWA, 크롬 엔진). 패키지명 `com.passionpeople.passio` 고정.

## 새 버전 만들기 (대표 PC)
서명키는 저장소에 없다 — 대표 개인 드라이브 `\TimeOfPassion\personal_folder\Passio_앱서명키` (잃어버리면 업데이트 불가).
도구: `C:\dev\tools` (JDK 17 · Android SDK 34 · Gradle 8.7).

```bash
export JAVA_HOME=C:/dev/tools/jdk-17.0.20.1+1 ANDROID_HOME=C:/dev/tools/android-sdk
export PASSIO_KEYSTORE_PATH=W:/Passio_앱서명키/passio-release.p12 PASSIO_KEYSTORE_PASSWORD=<읽어주세요.txt>
export PASSIO_VERSION_NAME=0.1.1 PASSIO_VERSION_CODE=2   # 코드는 매번 +1
cmd //c "C:\dev\tools\gradle-8.7\bin\gradle.bat assembleRelease --no-daemon"
gh release create v0.1.1 app/build/outputs/apk/release/app-release.apk#passio.apk
```
받는 주소(고정): https://github.com/timeofpassion/passio-android/releases/latest/download/passio.apk
