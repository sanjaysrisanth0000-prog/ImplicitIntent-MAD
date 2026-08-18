# Ex.No:3a Develop program to create a text field and a button “Navigate”. When you enter “www.gmail.com” and press navigate button it should open google page using Implicit Intents.


## AIM:

To create a navigate button using Implicit Intent to display the gmail page using Android Studio.

## EQUIPMENTS REQUIRED:

Latest Version Android Studio

## ALGORITHM:



## PROGRAM:

/*
Program to print the text “Implicitintent”.
Developed by:
Registeration Number :
*/

program:
activity.xml
```
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/main"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <EditText
        android:id="@+id/editText"
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:layout_margin="8dp"
        android:hint="https://google.com"
        android:inputType="textUri"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toStartOf="@+id/btn"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

    <Button
        android:id="@+id/btn"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_margin="8dp"
        android:text="Go"
        app:layout_constraintBottom_toBottomOf="@+id/editText"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintTop_toTopOf="@+id/editText" />

</androidx.constraintlayout.widget.ConstraintLayout>
```
mainactivity.java

```
package com.example.experiment2;

import android.content.Intent;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;

import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        EditText editText = findViewById(R.id.editText);
        Button button = findViewById(R.id.btn);

        button.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                String url = editText.getText().toString();
                if (!url.isEmpty()) {
                    if (!url.startsWith("http://") && !url.startsWith("https://")) {
                        url = "https://" + url;
                    }
                    
                    Intent intent = new Intent(MainActivity.this, WebViewActivity.class);
                    intent.putExtra("url", url);
                    startActivity(intent);
                }
            }
        });
    }
}
```

## OUTPUT

<img width="1916" height="1078" alt="Screenshot 2026-07-27 144328" src="https://github.com/user-attachments/assets/759c114b-0547-4178-9c5a-7623f8047b5b" />


<img width="1919" height="1079" alt="image" src="https://github.com/user-attachments/assets/c4752982-8900-4367-b659-71ca13746cb0" />


<img width="1917" height="1078" alt="Screenshot 2026-07-27 144841" src="https://github.com/user-attachments/assets/ad50f544-b5b3-450a-aa63-148e3ac50515" />


## RESULT
Thus a Simple Android Application create a navigate button using Implicit Intent to display the gmail page using Android Studio is developed and executed successfully.


