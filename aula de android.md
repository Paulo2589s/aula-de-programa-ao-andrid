(activity)
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/main"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    tools:context=".MainActivity">

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="rafa abilio" />

    <TextView
        android:id="@+id/txTitulo"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_gravity="center"

        android:layout_marginBottom="20dp"
        android:text="Calculadora"
        android:textColor="#09B765"
        android:textSize="30dp" />

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Digite um número:" />

    <EditText
        android:id="@+id/txNumero1"
        android:layout_width="match_parent"
        android:layout_height="wrap_content" />

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Digite outro número:" />

    <EditText
        android:id="@+id/txNumero2"
        android:layout_width="match_parent"
        android:layout_height="wrap_content" />
<Button
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:onClick="elevarAcCubo"
    android:text="elevarAcCubo"/>

    <Button
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Somar"
        android:backgroundTint="#000000"
        android:onClick="fazerSoma"/>

    <Button
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Subtrair"
        android:backgroundTint="#010301"
        android:onClick="fazerSubtrção"/>

    <Button
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Multiplicar"
        android:backgroundTint="#000000"
        android:onClick="fazerMultiplicação"/>

    <Button
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:backgroundTint="#000000"
        android:text="Dividir"
        android:onClick="fazerDivisao"/>



        />
</LinearLayout>


(MainActivicy)

package com.example.myapplication;

import android.os.Bundle;
import android.view.View;
import android.widget.EditText;
import android.widget.Toast;

import androidx.activity.EdgeToEdge;
import androidx.appcompat.app.AppCompatActivity;
import androidx.core.graphics.Insets;
import androidx.core.view.ViewCompat;
import androidx.core.view.WindowInsetsCompat;

public class MainActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        EdgeToEdge.enable(this);
        setContentView(R.layout.activity_main);
        ViewCompat.setOnApplyWindowInsetsListener(findViewById(R.id.main), (v, insets) -> {
            Insets systemBars = insets.getInsets(WindowInsetsCompat.Type.systemBars());
            v.setPadding(systemBars.left, systemBars.top, systemBars.right, systemBars.bottom);
            return insets;
        });
    }


    public void fazerSoma(View view) {
        //Toast.makeText(this, "Tralalelo tralala", Toast.LENGTH_LONG).show();
        EditText txn1 = findViewById(R.id.txNumero1);
        EditText txn2 = findViewById(R.id.txNumero2);

        int soma = Integer.parseInt(txn1.getText().toString()) + Integer.parseInt(txn2.getText().toString());

        String resultado = String.format("%d", soma);

        Toast.makeText(this, resultado, Toast.LENGTH_LONG).show();

    }

    public void fazerSubtrção(View view) {
        EditText txn1 = findViewById(R.id.txNumero1);
        EditText txn2 = findViewById(R.id.txNumero2);

        int subtração = Integer.parseInt(txn1.getText().toString()) - Integer.parseInt(txn2.getText().toString());

        String resultado = String.format("%d", subtração);

        Toast.makeText(this, resultado, Toast.LENGTH_LONG).show();

    }

    public void fazerMultiplicação(View view) {
        EditText txn1 = findViewById(R.id.txNumero1);
        EditText txn2 = findViewById(R.id.txNumero2);

        int multiplicação = Integer.parseInt(txn1.getText().toString()) * Integer.parseInt(txn2.getText().toString());

        String resultado = String.format("%d", multiplicação);

        Toast.makeText(this, resultado, Toast.LENGTH_LONG).show();
    }

    public void fazerDivisao(View view) {
        EditText txn1 = findViewById(R.id.txNumero1);
        EditText txn2 = findViewById(R.id.txNumero2);

        int divisao = Integer.parseInt(txn1.getText().toString()) / Integer.parseInt(txn2.getText().toString());

        String resultado = String.format("%d", divisao);

        Toast.makeText(this, resultado, Toast.LENGTH_LONG).show();
    }

    public void elevarAcCubo(View view) {
        EditText txn1 = findViewById(R.id.txNumero1);
        EditText txn2 = findViewById(R.id.txNumero2);

        int elevarAcCubo= Integer.parseInt(txn1.getText().toString()) * Integer.parseInt(txn1.getText().toString()) * Integer.parseInt(txn1.getText().toString());

        String resultado = String.format("%d", elevarAcCubo);

        Toast.makeText(this, resultado, Toast.LENGTH_LONG).show();
    }
}



