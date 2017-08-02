# [Android] 하나의 프로젝트에서 여러개 Menifest 사용하기

## 프로젝트 gradle

```
android {
	productFlavors {
        google {
            applicationIdSuffix ".google"
            targetSdkVersion 23
            versionCode 206
            versionName "1.4.33.1"
            manifestPlaceholders = [app_name : "APP_NAME",
                                    kakao_key : "KAKAO_KEY1",
                                    igaworks_key : "IGAWORKS_KEY1",
                                    igaworks_hash : "IGAWORKS_HASH1"]
            sourceSets {
                main {
                    manifest.srcFile 'src/google/AndroidManifest.xml'
                }
            }
        }

        origin {
            applicationIdSuffix ".plus"
            targetSdkVersion Integer.parseInt(project.TARGET_VER)
            versionCode 206
            versionName "2.0.20.1"
            manifestPlaceholders = [app_name : "APP_NAME",
                                    kakao_key : "KAKAO_KEY2",
                                    igaworks_key : "IGAWORKS_KEY2",
                                    igaworks_hash : "IGAWORKS_HASH2"]
            sourceSets {
                main{
                    manifest.srcFile 'src/origin/AndroidManifest.xml'
                }
            }
        }

        tstore {
            applicationIdSuffix ".tstore"
            targetSdkVersion 23
            versionCode 207
            versionName "2.0.21.1"
            manifestPlaceholders = [app_name : "APP_NAME",
                                    kakao_key : "KAKAO_KEY3",
                                    igaworks_key : "IGAWORKS_KEY3",
                                    igaworks_hash : "IGAWORKS_HASH3"]
            sourceSets {
                main {
                    manifest.srcFile 'src/tstore/AndroidManifest.xml'
                }
            }
        }
    }

}


```
* applicationIdSuffix 는 패키지명 다음에 붙는다.
* manifestPlaceholders key-value 형식으로 google, origin, tstore 의 AndroidManifest에서 ${app_name} 으로 사용한다


## 프로젝트 구조

![](https://github.com/khjoon0204/android_multi_menifest/blob/master/image2.png)

## 패키지 명
모든 프로젝트 
```
package="com.toptooncomics.topviewer"
```
