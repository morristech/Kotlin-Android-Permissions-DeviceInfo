# Kotlin-Android-Permissions-DeviceInfo
 [![API](https://img.shields.io/badge/API-15%2B-brightgreen.svg?style=flat)](https://android-arsenal.com/api?level=15) [![Hex.pm](https://img.shields.io/hexpm/l/plug.svg?maxAge=2592000)](http://www.apache.org/licenses/LICENSE-2.0)
 [![Android Arsenal](https://img.shields.io/badge/Android%20Arsenal-Kotlin--Android--Permissions-green.svg?style=true)](https://android-arsenal.com/details/1/4511)
 
The easiest Kotlin Library for Android Runtime Permissions &amp; Device Info.
#ScreenShots
<img src="https://github.com/AnirudhLoya/Kotlin-Android-Permissions-DeviceInfo/blob/master/call_permission.png" width="300"/>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img src="https://github.com/AnirudhLoya/Kotlin-Android-Permissions-DeviceInfo/blob/master/device-2016-09-24-183505.png" width="300"/> 


#Usage For Kotlin
Your Activity must extends with PermissionsActivity
```
class MainActivity : PermissionsActivity()
``` 
```java
  requestPermissions(Manifest.permission.CALL_PHONE, object : PermissionCallBack {
                override fun permissionGranted() {
                    super.permissionGranted()
                    Log.v("Call permissions", "Granted")
                }

                override fun permissionDenied() {
                    super.permissionDenied()
                    Log.v("Call permissions", "Denied")
                }
            })

 ```
#Sample MainActvity.k
```
import android.Manifest
import android.os.Bundle
import android.util.Log
import io.vrinda.kotlinpermissions.PermissionCallBack
import io.vrinda.kotlinpermissions.PermissionsActivity
import kotlinx.android.synthetic.main.activity_main.*

class MainActivity : PermissionsActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)

        callPermission.setOnClickListener {
            requestPermissions(Manifest.permission.CALL_PHONE, object : PermissionCallBack {
                override fun permissionGranted() {
                    super.permissionGranted()
                    Log.v("Call permissions", "Granted")
                }

                override fun permissionDenied() {
                    super.permissionDenied()
                    Log.v("Call permissions", "Denied")
                }
            })
        }
        cameraPermission.setOnClickListener {
            requestPermissions(arrayOf(android.Manifest.permission.CAMERA, android.Manifest.permission.WRITE_EXTERNAL_STORAGE), object : PermissionCallBack {
                override fun permissionGranted() {
                    super.permissionGranted()
                    Log.v("Camera permissions", "Denied")
                }

                override fun permissionDenied() {
                    super.permissionDenied()
                    Log.v("Camera permissions", "Denied")
                }
            })
        }

    }
}
```
#Dependencies
Add this to your app build.gradle
```
compile 'io.vrinda.kotlinpermissions:kotlinpermissions:1.0'
```

[![Android Arsenal](https://img.shields.io/badge/Android%20Arsenal-Kotlin--Android--Permissions-green.svg?style=true)]
