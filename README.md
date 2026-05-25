# Ex.No:2a Develop program to create a text field and a button “Navigate”. When you enter “www.gmail.com” and press navigate button it should open google page using Implicit Intents.


## AIM:

To create a navigate button using Implicit Intent to display the gmail page using Android Studio.

## EQUIPMENTS REQUIRED:

Latest Version Android Studio

## ALGORITHM:

1. **Start the project:** Create a new Android project in Android Studio.

2. **Design the UI:** In `activity_main.xml`, add an `EditText` (to accept the URL input) and a `Button` (to trigger the navigation).

3. **Initialize components:** In `MainActivity.java`, map the `EditText` and `Button` variables to their respective XML IDs using `findViewById()`.

4. **Set click listener:** Attach an `OnClickListener` to the button to listen for user click events.

5. **Get input:** Inside the `onClick` method, extract the text entered in the `EditText` and convert it to a string.

6. **Create implicit intent:** Instantiate an `Intent` with the action `Intent.ACTION_VIEW` and pass the parsed URL string using `Uri.parse()`.

7. **Start activity:** Call `startActivity(intent)` to trigger the OS to open the webpage in an available web browser.

8. **Stop:** Run and test the application.

## PROGRAM:
```
/*
Program to print the text “Implicitintent”.
Developed by: Ashwin Subash M
Registeration Number : 212224220109
*/
```
## MainActivity.java
```java

package com.example.implicit;

import android.content.Intent;
import android.net.Uri;
import android.os.Bundle;
import android.widget.Button;
import android.widget.EditText;

import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    EditText editText;
    Button button;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        button = findViewById(R.id.button);
        editText = findViewById(R.id.editText);

        button.setOnClickListener(view -> {
            String url = editText.getText().toString();

            Intent intent = new Intent(
                    Intent.ACTION_VIEW,
                    Uri.parse(url)
            );

            startActivity(intent);
        });
    }
}
```
## activity_main.xml
```
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/main"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <TextView
        android:id="@+id/textView2"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Website Navigation"
        android:textSize="22sp"
        android:textStyle="bold"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintAStart_toStartOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        android:layout_marginTop="80dp" />

    <EditText
        android:id="@+id/editText"
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:hint="Enter website (e.g., google.com)"
        android:inputType="textUri"
        android:padding="12dp"
        app:layout_constraintTop_toBottomOf="@id/textView2"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        android:layout_marginTop="30dp"
        android:layout_marginStart="20dp"
        android:layout_marginEnd="20dp" />

    <Button
        android:id="@+id/button"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Navigate"
        app:layout_constraintTop_toBottomOf="@id/editText"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        android:layout_marginTop="20dp" />

</androidx.constraintlayout.widget.ConstraintLayout>

```
## OUTPUT

<img width="1914" height="1027" alt="EXP_02_MU" src="https://github.com/user-attachments/assets/2a73c7d8-208e-42da-bdcc-bcc3cd4e76de" />

<img width="1919" height="1032" alt="Screenshot 2026-05-25 114204" src="https://github.com/user-attachments/assets/51363ae6-678e-42b1-8bd1-405b400a5a89" />

<img width="1917" height="1032" alt="Screenshot 2026-05-25 115415" src="https://github.com/user-attachments/assets/600cf24b-b540-4c17-b8af-2c2d18778303" />


## RESULT
Thus a Simple Android Application create a navigate button using Implicit Intent to display the gmail page using Android Studio is developed and executed successfully.


