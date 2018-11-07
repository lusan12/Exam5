## Universidad Nacional Autónoma de México
### Facultad de Ingeniería

### Técnicas de Programación
#### Exámen 5 ✔✔

- #### Sánchez Ruiz Luis Armando
- #### Uribe Serralde Armando


#### Analisis de requisitos:

### Objetivo

Desarrollar una App que pueda calcular el área estas tres figuras geométricas.

- Circulo
- Cuadrado
- Triángulo

#### Requisitos:

- ¿Qué tipo de números?

Todos los naturales y racionales .

- ¿ Se necesita guardar resultados anteriores?

No

- ¿ Debe de contener un boton para borrar los campos?

Si

- ¿Debe de notificar la App si falta algún dato?

Si

- ¿Debe de realizar operaciones simultaneas?

No

#### Arquitectura 

                
            package com.google.android.instantapps.samples.hello.feature;

import android.content.Intent;
import android.os.Bundle;
import android.support.v7.app.AppCompatActivity;
import android.view.View;
import android.widget.EditText;
import android.widget.RadioButton;
import android.widget.TextView;

import javax.xml.transform.Result;

/**
 * This Activity displays a simple hello world text and a button to open the GoodbyeActivity.
 */
public class HelloActivity extends AppCompatActivity {

    private EditText editText1;
    private EditText editText2;
    private TextView textView1;
    private RadioButton rButton1;
    private RadioButton rButton2;

    private RadioButton rButton3;




    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_hello);
        findViewById(R.id.button).setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                startActivity(new Intent(HelloActivity.this, GoodbyeActivity.class));
            }
        });

        editText1 = (EditText)findViewById(R.id.txt_num1);
        editText2 = (EditText)findViewById(R.id.txt_num2);
        textView1 = (TextView) findViewById(R.id.txt_Resultado);
        rButton1 = (RadioButton)findViewById(R.id.radioButtonCuadrado);
        rButton2 = (RadioButton)findViewById(R.id.radioButtonTriangulo);
        rButton3 = (RadioButton)findViewById(R.id.radioButtonCirculo);

    }
    public  void Triangulo(View view)
    {



        String Val1T = editText1.getText().toString();
        String Val2T = editText2.getText().toString();
            double Val1Int = Double.parseDouble(Val1T);
            double Val2Int = Double.parseDouble(Val2T);
            double Result = 0;

            Result = (Val1Int * Val2Int)/2;
            String Restring = String.valueOf(Result);
            textView1.setText(Restring);
        }
    public  void Circulo(View view)
    {



        String Val1T = editText1.getText().toString();
        String Val2T = editText2.getText().toString();

        double Val1Int = Double.parseDouble(Val1T);
        double Val2Int = 3.1416;
        double Result = 0;

        Result = Val1Int * Val1Int * Val2Int ;
        String Restring = String.valueOf(Result);
        textView1.setText(Restring);
    }



    public  void Cuadrado(View view)
    {
        String Val1T = editText1.getText().toString();
        String Val2T = editText2.getText().toString();
        double Val1Int = Double.parseDouble(Val1T);
        double Val2Int = Double.parseDouble(Val2T);

        double Result = 0;
        Result = Val1Int * Val2Int;
        String Restring = String.valueOf(Result);
        textView1.setText(Restring);

    }
    public  void leer(View view)
    {
        if(rButton3.isChecked() == true )
        {
            if(editText1.length() == 0 || editText1.getText().toString() == "." || editText1.getText().toString() == "-")
            {//|| editText1.getText().toString() != "0"|| editText1.getText().toString() != "1" || editText1.getText().toString() != "2"|| editText1.getText().toString() != "3"|| editText1.getText().toString() != "4"|| editText1.getText().toString() != "5"|| editText1.getText().toString() != "6"|| editText1.getText().toString() != "7"|| editText1.getText().toString() != "8"|| editText1.getText().toString() != "9"
                if(editText2.length() == 0  ) {
                    textView1.setText("ningun dato");

                }
                else{
                    textView1.setText("Falta un  dato");

                }

            }
            else if (editText1.getText().toString() == "." ) {
                textView1.setText("ningun dato");

            }
            else{
                Circulo(view);
            }

        }

        if(rButton2.isChecked() == true )
        {
            if(editText1.length() == 0   || editText1.getText().toString() == "." || editText1.getText().toString() == "-")
            {//|| editText1.getText().toString() != "0"|| editText1.getText().toString() != "1" || editText1.getText().toString() != "2"|| editText1.getText().toString() != "3"|| editText1.getText().toString() != "4"|| editText1.getText().toString() != "5"|| editText1.getText().toString() != "6"|| editText1.getText().toString() != "7"|| editText1.getText().toString() != "8"|| editText1.getText().toString() != "9"
                if(editText2.length() == 0) {
                    textView1.setText("ningun dato");

                }
                else{
                    textView1.setText("Falta un  dato");

                }

            }
           else if (editText1.getText().toString() == "." ) {
                textView1.setText("ningun dato");

            }
            else{
                if(editText1.length() != 0 && editText2.length() == 0) {
                    textView1.setText("Falta un  dato");

                }
                else{
                    Triangulo(view);

                }

            }

        }
        if(rButton1.isChecked() == true)
        {
            /*    if(editText1.isActivated() == true)
                {
                    if(editText2.isActivated()== true) {
                        textView1.setText("ningun dato");
                    }
                }
                else {

                    Cuadrado(view);
                }
        }*/
            if(editText1.length() == 0 || editText1.getText().toString() == "." || editText1.getText().toString() == "-")
            {//|| editText1.getText().toString() != "0"|| editText1.getText().toString() != "1" || editText1.getText().toString() != "2"|| editText1.getText().toString() != "3"|| editText1.getText().toString() != "4"|| editText1.getText().toString() != "5"|| editText1.getText().toString() != "6"|| editText1.getText().toString() != "7"|| editText1.getText().toString() != "8"|| editText1.getText().toString() != "9"
                if(editText2.length() == 0) {
                    textView1.setText("ningun dato");

                }
                else{
                    textView1.setText("Falta un  dato");

                }

            }
            else if (editText1.getText().toString() == "." ) {
                textView1.setText("ningun dato");

            }
            else{if(editText1.length() != 0 && editText2.length() == 0) {
                textView1.setText("Falta un  dato");

            }
            else{
                Cuadrado(view);

            }
            }

        }
    }
    public void borrar(View view)
    {
        textView1.setText(null);
        editText1.setText(null);
        editText2.setText(null);
    }


}


#### Diseño SW

#### Aplicación

#### Pruebas

