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
            manifestPlaceholders = [app_name : "탑툰",
                                    kakao_key : "40324bafc392f49b7f052724afd17a71",
                                    igaworks_key : "573659521",
                                    igaworks_hash : "dd6839e3f337411e"]
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
            manifestPlaceholders = [app_name : "PLUS",
                                    kakao_key : "2b4cfccb471797c3b104f7032cc62784",
                                    igaworks_key : "106643164",
                                    igaworks_hash : "60dd9e4a99974bc9"]
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
            manifestPlaceholders = [app_name : "탑툰",
                                    kakao_key : "40324bafc392f49b7f052724afd17a71",
                                    igaworks_key : "216500354",
                                    igaworks_hash : "7f3e03c7d4e14d01"]
            sourceSets {
                main {
                    manifest.srcFile 'src/tstore/AndroidManifest.xml'
                }
            }
        }
    }

}


```

## 프로젝트 구조

![](https://github.com/khjoon0204/android_multi_menifest/blob/master/image2.png)

## 패키지 명
모든 프로젝트 
```
package="com.toptooncomics.topviewer"
```
