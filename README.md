
# Ex.No:03 Design an android application Send SMS using Intent.


## AIM:

To create and design an android application Send SMS using Intent using Android Studio.

## EQUIPMENTS REQUIRED:

Android Studio(Latest Version)

## ALGORITHM:

Step 1: Open Android Stdio and then click on File -> New -> New project.

Step 2: Then type the Application name as smsintent and click Next. 

Step 3: Then select the Minimum SDK as shown below and click Next.

Step 4: Then select the Empty Activity and click Next. Finally click Finish.

Step 5: Design layout in activity_main.xml.

Step 6: Send SMS and Display details give in MainActivity file.

Step 7: Save and run the application.

## PROGRAM:
```
/*
Program to create and design an android application Send SMS using Intent.
Developed by: KAMLESH Y
Registeration Number :212224100029
*/
```
## MAIN_ACTIVITY.JAVA
```java
package com.example.smssender;

import android.app.Activity;
import android.content.Intent;
import android.net.Uri;
import android.os.Bundle;
import android.widget.Button;
import android.widget.EditText;

public class MainActivity extends Activity {

    EditText etPhone, etMessage;
    Button btnSendSMS;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);

        setContentView(R.layout.main_activity);

        etPhone = findViewById(R.id.etPhone);
        etMessage = findViewById(R.id.etMessage);
        btnSendSMS = findViewById(R.id.btnSendSMS);

        btnSendSMS.setOnClickListener(v -> {

            String phoneNumber = etPhone.getText().toString().trim();
            String message = etMessage.getText().toString().trim();

            Intent intent = new Intent(Intent.ACTION_SENDTO);

            intent.setData(
                    Uri.parse("smsto:" + phoneNumber)
            );

            intent.putExtra(
                    "sms_body",
                    message
            );

            startActivity(intent);
        });
    }
}
```
### MAIN_ACTIVITY.XML
```xml
<?xml version="1.0" encoding="utf-8"?>

<LinearLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:padding="20dp">

    <TextView
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Send SMS"
        android:textSize="24sp"
        android:textStyle="bold"
        android:gravity="center"
        android:padding="16dp" />

    <EditText
        android:id="@+id/etPhone"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="Enter Phone Number"
        android:inputType="phone" />

    <EditText
        android:id="@+id/etMessage"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="Enter Message"
        android:inputType="textMultiLine"
        android:minLines="3" />

    <Button
        android:id="@+id/btnSendSMS"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Send SMS" />

</LinearLayout>
```
## OUTPUT

<img width="1536" height="916" alt="image" src="https://github.com/user-attachments/assets/c97c405b-bbe2-4b4b-849e-9ecb16a76097" />

<img width="1536" height="912" alt="image" src="https://github.com/user-attachments/assets/be24c503-2cf3-4254-b402-b1f2905982ec" />





## RESULT
Thus a Simple Android Application create and design an android application Send SMS using Intent using Android Studio is developed and executed successfully.
