# Gues_a_Number
Guess a random generated number between 1 and 100
Java code:

package com.example.higherorlower;

import android.support.v7.app.AppCompatActivity;
import android.os.Bundle;
import android.util.Log;
import android.view.View;
import android.widget.EditText;
import android.widget.Toast;

import java.util.*;

public class MainActivity extends AppCompatActivity {

    int randomNumber;

    public void generateRandomNumber()
    {
        Random rand = new Random();
        randomNumber= rand.nextInt(100)+1;
    }

    public void guess(View view)
    {
        EditText editText = (EditText) findViewById(R.id.editTextNumber);

        int guessValue = Integer.parseInt(editText.getText().toString());

        String message="";

        if(guessValue>randomNumber)
        {
            message  = "lower";
        }
        if(guessValue<randomNumber)
        {
            message = "higher";
        }
        if(guessValue == randomNumber)
        {
            message = "You've got it!!! Try again...";
            generateRandomNumber();
        }

        Toast.makeText(this, message, Toast.LENGTH_SHORT).show();
        Log.i("Entered Value", editText.getText().toString());
        Log.i("Info", Integer.toString(randomNumber));


    }
    @Override



    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        generateRandomNumber();
    }
}

XML:

<?xml version="1.0" encoding="utf-8"?>
<android.support.constraint.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <TextView
        android:id="@+id/textView"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginStart="30dp"
        android:layout_marginLeft="30dp"
        android:layout_marginTop="50dp"
        android:layout_marginEnd="200dp"
        android:layout_marginRight="20dp"
        android:layout_marginBottom="654dp"
        android:text="I am thinking about a number between 1 and 100"
        android:textSize="18sp"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.091"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.666" />

    <TextView
        android:id="@+id/textView2"
        android:layout_width="wrap_content"
        android:layout_height="19dp"
        android:layout_marginStart="150dp"
        android:layout_marginLeft="150dp"
        android:layout_marginTop="50dp"
        android:layout_marginEnd="150dp"
        android:layout_marginRight="150dp"
        android:layout_marginBottom="600dp"
        android:text="Can you guess it??"
        android:textSize="18sp"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/textView" />

    <EditText
        android:id="@+id/editTextNumber"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginStart="96dp"
        android:layout_marginLeft="96dp"
        android:layout_marginTop="89dp"
        android:layout_marginEnd="105dp"
        android:layout_marginRight="105dp"
        android:layout_marginBottom="458dp"
        android:ems="10"
        android:inputType="number"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/textView2" />

    <Button
        android:id="@+id/button"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginStart="154dp"
        android:layout_marginLeft="154dp"
        android:layout_marginTop="44dp"
        android:layout_marginEnd="169dp"
        android:layout_marginRight="169dp"
        android:layout_marginBottom="366dp"
        android:onClick="guess"
        android:text="Try"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/editTextNumber" />

</android.support.constraint.ConstraintLayout>
