# Ex.No: 6 Develop a application to add animations to ImageView,Move,blink,fade,clockwise,zoom,slide operations are perform in android studio.


## AIM:

To develop a application to add animation to imageview,move,blink,fade,clockwise,zoom,slide operation using Android Studio.

## EQUIPMENTS REQUIRED:

Android Studio(Latest Version)

## ALGORITHM:
```
1.Start Android Studio → Create a New Project (Empty Activity).

2.Design Layout

3.Add an ImageView and Buttons for each animation (Move, Blink, Fade, Clockwise, Zoom, Slide) in activity_main.xml.

4.Create Animation Files

5.In res/anim/, create XML files: move.xml, blink.xml, fade.xml, clockwise.xml, zoom.xml, slide.xml.

6.Define each animation using <translate>, <alpha>, <rotate>, or <scale> tags.

7.Write Java Code

8.In MainActivity, link all buttons and the ImageView.

9.Use AnimationUtils.loadAnimation() to load animations.

10.Start animation with imageView.startAnimation(animation); inside each button’s onClickListener.

11.Run the App

12.Select each button → observe the animation on ImageView.

13.End.
```


## PROGRAM:
```
/*
Program to display animation operation”.
Developed by:theja sree g
Registeration Number :212224110056
*/
```
## activity_main.xml:
```
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:orientation="vertical"
    android:gravity="center"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:padding="16dp">

    <ImageView
        android:id="@+id/imageView"
        android:layout_width="200dp"
        android:layout_height="200dp"
        android:src="@drawable/ic_launcher_foreground"
        android:layout_marginBottom="30dp" />

    <Button
        android:id="@+id/btnMove"
        android:text="Move"
        android:layout_width="match_parent"
        android:layout_height="wrap_content" />

    <Button
        android:id="@+id/btnBlink"
        android:text="Blink"
        android:layout_width="match_parent"
        android:layout_height="wrap_content" />

    <Button
        android:id="@+id/btnFade"
        android:text="Fade"
        android:layout_width="match_parent"
        android:layout_height="wrap_content" />

    <Button
        android:id="@+id/btnClockwise"
        android:text="Clockwise"
        android:layout_width="match_parent"
        android:layout_height="wrap_content" />

    <Button
        android:id="@+id/btnZoom"
        android:text="Zoom"
        android:layout_width="match_parent"
        android:layout_height="wrap_content" />

    <Button
        android:id="@+id/btnSlide"
        android:text="Slide"
        android:layout_width="match_parent"
        android:layout_height="wrap_content" />

</LinearLayout>
```
## move.xml:
```
<translate xmlns:android="http://schemas.android.com/apk/res/android"
    android:fromXDelta="0%"
    android:toXDelta="75%"
    android:duration="800" />
```
## blink.xml:
```
<alpha xmlns:android="http://schemas.android.com/apk/res/android"
    android:fromAlpha="1.0"
    android:toAlpha="0.0"
    android:duration="300"
    android:repeatCount="infinite"
    android:repeatMode="reverse" />
```
## fade.xml:
```
<alpha xmlns:android="http://schemas.android.com/apk/res/android"
    android:fromAlpha="0.0"
    android:toAlpha="1.0"
    android:duration="2000" />
```
## clockwise.xml:
```
<rotate xmlns:android="http://schemas.android.com/apk/res/android"
    android:fromDegrees="0"
    android:toDegrees="360"
    android:pivotX="50%"
    android:pivotY="50%"
    android:duration="1000" />
```
## zoom.xml:
```
<scale xmlns:android="http://schemas.android.com/apk/res/android"
    android:fromXScale="1.0"
    android:toXScale="2.0"
    android:fromYScale="1.0"
    android:toYScale="2.0"
    android:pivotX="50%"
    android:pivotY="50%"
    android:duration="1000"
    android:repeatCount="1"
    android:repeatMode="reverse" />
```
## slide.xml:
```
<translate xmlns:android="http://schemas.android.com/apk/res/android"
    android:fromXDelta="-100%"
    android:toXDelta="0%"
    android:duration="700" />
```
## MainActivity.java:
```
package com.example.animationapp;

import androidx.appcompat.app.AppCompatActivity;
import android.os.Bundle;
import android.view.View;
import android.view.animation.Animation;
import android.view.animation.AnimationUtils;
import android.widget.Button;
import android.widget.ImageView;

public class MainActivity extends AppCompatActivity {

    ImageView image;
    Button move, blink, fade, clockwise, zoom, slide;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        image = findViewById(R.id.imageView);
        move = findViewById(R.id.btnMove);
        blink = findViewById(R.id.btnBlink);
        fade = findViewById(R.id.btnFade);
        clockwise = findViewById(R.id.btnClockwise);
        zoom = findViewById(R.id.btnZoom);
        slide = findViewById(R.id.btnSlide);

        move.setOnClickListener(v -> startAnimation(R.anim.move));
        blink.setOnClickListener(v -> startAnimation(R.anim.blink));
        fade.setOnClickListener(v -> startAnimation(R.anim.fade));
        clockwise.setOnClickListener(v -> startAnimation(R.anim.clockwise));
        zoom.setOnClickListener(v -> startAnimation(R.anim.zoom));
        slide.setOnClickListener(v -> startAnimation(R.anim.slide));
    }

    private void startAnimation(int animId) {
        Animation animation = AnimationUtils.loadAnimation(getApplicationContext(), animId);
        image.startAnimation(animation);
    }
}
```
## OUTPUT

<img width="1920" height="1080" alt="Screenshot (209)" src="https://github.com/user-attachments/assets/b6d4a7a9-cd27-4059-80e3-fe507a449c04" />

<img width="1920" height="1080" alt="Screenshot (211)" src="https://github.com/user-attachments/assets/1449162e-c9fd-473c-adc6-ce206e733a2a" />

<img width="1920" height="1080" alt="Screenshot (212)" src="https://github.com/user-attachments/assets/9dadf314-bddb-42a1-8cbd-40d61193a5e7" />

<img width="1920" height="1080" alt="Screenshot (213)" src="https://github.com/user-attachments/assets/5f702c21-6604-4a27-8912-98c02ef7882e" />

<img width="1920" height="1080" alt="Screenshot (215)" src="https://github.com/user-attachments/assets/c48731ab-9fe0-4f3a-ba52-57341e538776" />

<img width="1920" height="1080" alt="Screenshot (216)" src="https://github.com/user-attachments/assets/45f5a58c-feeb-4c14-ad97-289f51f5049f" />

## RESULT
The application successfully performs multiple animations—Move, Blink, Fade, Clockwise, Zoom, and Slide—on an ImageView.
