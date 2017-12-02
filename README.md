# Multiple-splash-screen-in-Android
Easy way to use Multiple Splash screen in any android application.


***Follow some instruction step by step:***
---

***Step 1:***
Create a project in Android Studio.

***Step 2:***
Create a new activity by right click `res` then click `New -> Activity -> Empty Activity` and name it 'Splash'

***Step 3:***
Create another new activity by right click `res` then click `New -> Activity -> Empty Activity` and name it 'Splash2'

***Step 4:***
Now open `AndroidManifest.xml` file and add below code.

```
        <activity android:name=".MainActivity">
            <intent-filter>
                <action android:name="android.intent.action.MAIN" />

                <category android:name="android.intent.category.DEFAULT" />
            </intent-filter>
        </activity>

        <activity
            android:name=".SplashActivity"
            android:theme="@style/Theme.AppCompat.Light.NoActionBar">
            <intent-filter>
                <action android:name="android.intent.action.MAIN" />

                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>
        </activity>
        
        <activity
            android:name=".Splash2Activity"
            android:theme="@style/Theme.AppCompat.Light.NoActionBar">
        </activity>
```

***Step 5:***
Now open `SplashActivity.java` class file and past below code into onCreate() method.

```
         new Handler().postDelayed(new Runnable(){
            @Override
            public void run() {
                /* Create an Intent that will start the Next-Splash-Activity. */
                Intent mainIntent = new Intent(getApplication(),Splash2Activity.class);
                startActivity(mainIntent);
                finish();
            }
        }, 2000);
```

***Step 6:***
Now open `Splash2Activity.java` class file and past below code into onCreate() method.

```
         new Handler().postDelayed(new Runnable(){
            @Override
            public void run() {
                /* Create an Intent that will start the Next-Splash-Activity. */
                Intent mainIntent = new Intent(getApplication(),MainActivity.class);
                startActivity(mainIntent);
                finish();
            }
        }, 2000);
```

***Step 7:***
Now disable back button press. So create a new method `onBackPressed()` in `Splash2Activity.java` 

***Step 8:***
Build and Run Application...... :D :D
