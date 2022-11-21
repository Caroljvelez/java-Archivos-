# java-Archivos-

package manejoarchivos;

import java.io.*;
import java.util.logging.Level;
import java.util.logging.Logger;

public class ManejoArchivos {

    public static void crearArchivos(String nombreArchivo) {

        File archivo = new File(nombreArchivo);
        try {
            PrintWriter salida = new PrintWriter(archivo);
            salida.close();//cerramos el archivo y lo creamos en el disco duro
            System.out.println("Se ha creado el archivo");
        } catch (FileNotFoundException ex) {
            ex.printStackTrace(System.out);

        }

    }

    public static void escribirArchivo(String nombreArchivo, String contenido) {
        File archivo = new File(nombreArchivo);
        try {
            PrintWriter salida = new PrintWriter(archivo);
            salida.println(contenido);
            salida.close();//cerramos el archivo y lo creamos en el disco duro
            System.out.println("Se ha escrito en el archivo");
        } catch (FileNotFoundException ex) {
            ex.printStackTrace(System.out);

        }
    }

    public static void anexarArchivo(String nombreArchivo, String contenido) {
        File archivo = new File(nombreArchivo);
        try {
            PrintWriter salida = new PrintWriter(new FileWriter(archivo, true));
            salida.println(contenido);
            salida.close();//cerramos el archivo y lo creamos en el disco duro
            System.out.println("Se ha anexado informacion en el archivo");
        } catch (FileNotFoundException ex) {
            ex.printStackTrace(System.out);

        } catch (IOException ex) {
            ex.printStackTrace(System.out);
        }
    }

    public static void leerArchivo(String nombreArchivo) {
        var archivo = new File(nombreArchivo);
        try {
            var entrada = new BufferedReader(new FileReader(archivo));
            var lectura = entrada.readLine(); //se lee una linea
            while (lectura != null){ //si es diferente a vacio entra al ciclo
                System.out.println("lectura = "+ lectura);//imprime lo que lee
                lectura = entrada.readLine();//sigue leyendo las lineas
            }
            entrada.close(); //cierra cuando ya no teien nada 
        } catch (FileNotFoundException ex) {
            ex.printStackTrace(System.out);
        } catch (IOException ex) {
            ex.printStackTrace(System.out);
        }
    }

}
