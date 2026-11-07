# Ex-1 DEVELOPING-A-BASIC-REGISTRATION-APPLICATION-ON-ANDROID-STUDIO
even_term_ii_2025-26

## NAME: Arsha Jith S J
## Register number: 212224220010

# Student Registration Application Using Android Studio

This experiment demonstrates the development of a basic Student Registration Application using Android Studio, Java, and XML.

## Aim
To develop a basic Student Registration Application in Android Studio using Java and XML to accept and display student details.


## Software Requirements
- Java JDK
- Android Studio
- Android SDK
- Android Virtual Device (AVD)
- Java Programming Language
- XML


## Step 1 – Create a New Android Project

1. Open Android Studio.
2. Select **New Project**.
3. Choose **Empty Views Activity**.
4. Enter the application name as StudentRegistration.
5. Select Java as the programming language.
6. Choose the minimum SDK version.
7. Click Finish to create the project.



## Step 2 – Design the User Interface (XML)

The user interface is designed using XML components.

### Components Used
- TextView – To display the heading and registration details.
- EditText – To enter student name, email, and phone number.
- RadioButton – To select gender.
- RadioGroup – To group the gender options.
- Button – To submit the registration details.
- ScrollView – To make the screen scrollable.

### XML Code

```
xml
<?xml version="1.0" encoding="utf-8"?>
<ScrollView xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent">

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:orientation="vertical"
        android:padding="20dp">

        <TextView
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="Student Registration"
            android:textSize="25sp"
            android:textStyle="bold"
            android:gravity="center"
            android:padding="15dp" />

        <EditText
            android:id="@+id/name"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:hint="Enter Name"
            android:inputType="textPersonName" />

        <EditText
            android:id="@+id/email"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:hint="Enter Email"
            android:inputType="textEmailAddress" />

        <EditText
            android:id="@+id/phone"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:hint="Enter Phone Number"
            android:inputType="phone" />

        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Select Gender"
            android:textSize="18sp"
            android:paddingTop="12dp" />

        <RadioGroup
            android:id="@+id/genderGroup"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:orientation="horizontal">

            <RadioButton
                android:id="@+id/male"
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:text="Male" />

            <RadioButton
                android:id="@+id/female"
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:text="Female" />
        </RadioGroup>

        <Button
            android:id="@+id/register"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="Register" />

        <TextView
            android:id="@+id/result"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:textSize="17sp"
            android:padding="15dp" />

    </LinearLayout>
</ScrollView>
```



## Step 3 – Write Java Code

The Java code is used to retrieve the entered details, validate the input, and display the registration result.

### Java Code

```
java
package com.example.studentregistration;

import android.os.Bundle;
import android.widget.Button;
import android.widget.EditText;
import android.widget.RadioGroup;
import android.widget.TextView;
import android.widget.Toast;

import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    EditText name, email, phone;
    RadioGroup genderGroup;
    Button register;
    TextView result;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        name = findViewById(R.id.name);
        email = findViewById(R.id.email);
        phone = findViewById(R.id.phone);
        genderGroup = findViewById(R.id.genderGroup);
        register = findViewById(R.id.register);
        result = findViewById(R.id.result);

        register.setOnClickListener(v -> {

            String n = name.getText().toString();
            String e = email.getText().toString();
            String p = phone.getText().toString();

            int selected = genderGroup.getCheckedRadioButtonId();

            if (n.isEmpty() || e.isEmpty() || p.isEmpty()
                    || selected == -1) {

                Toast.makeText(MainActivity.this,
                        "Please fill all details",
                        Toast.LENGTH_SHORT).show();

            } else {

                String gender;

                if (selected == R.id.male) {
                    gender = "Male";
                } else {
                    gender = "Female";
                }

                result.setText(
                        "Registration Successful!\n\n" +
                        "Name: " + n + "\n" +
                        "Email: " + e + "\n" +
                        "Phone: " + p + "\n" +
                        "Gender: " + gender
                );
            }
        });
    }
}
```



## Step 4 – Run the Application

1. Open the Android Studio project.
2. Connect an Android device or start an Android Virtual Device.
3. Click the Run button.
4. The Student Registration Application will be displayed.
5. Enter the student name, email, and phone number.
6. Select the gender.
7. Click the Register button.
8. The entered details will be displayed on the screen.

## Output

<img width="1331" height="835" alt="Screenshot 2026-11-07 150524" src="https://github.com/user-attachments/assets/aa1aeff2-749f-4882-a60a-063356a192d5" />


## Result

Thus, the Student Registration Application was successfully developed and executed using Android Studio with Java and XML. The application accepts student details, validates the input, and displays the registration information.


The basic Android application was successfully created using Android Studio. The experiment helped to understand XML user interface design, Java programming, user input handling, and button click events in Android application development.
