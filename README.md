# Menu-Programa-T.I.S.A.
Un programa que tiene 3 funciones diferentes 


-	Al seleccionar la opción 1, debe solicitar un día de la semana y nos diga si es un día laboral o no, tomando en cuenta que los días laborales serán considerandos desde lunes a viernes (ambos inclusive).

-	Al seleccionar la opción 2, debe solicitar un número entero (debe estar entre 33 y 255 extremos inclusive) y luego debe mostrar el correspondiente carácter asociado al código ascii. Por ejemplo: si el usuario ingresa 300, debe indicar que el número no corresponde; ahora si ingresa 64, debe mostrar “64 corresponde a @”

-	Al seleccionar la opción 3, debe solicitar un número entero positivo y luego debe mostrar “La tabla de multiplicar del número XX es: ” (Deberá mostrar una tabla de multiplicar del 1 al 15).
-	


package tisa;

import java.util.Scanner;

public class Menuprograma {

    public static void main(String[] args) {
        int opcion;

        Scanner guti = new Scanner(System.in);

        opcion = 1;

        while (opcion != 4) {
            System.out.print("\n********\n" +
                    "TI S.A\n" +
                    "********\n" +
                    "1. Dia laboral\n" +
                    "2. Código Ascii\n" +
                    "3. Tabla de multiplicar, según número ingresado (mostrar hasta el 15)\n" +
                    "4. Salir\n" +
                    "\tElija Opción: ");

            opcion = guti.nextInt();

            switch (opcion) {
                case 1:
                    System.out.print("Ingrese un día de la semana (Lunes = 1, Martes = 2, ..., Viernes = 5): ");

                    int numeroDia = guti.nextInt();
                    boolean esDiaLaboral = esDiaLaboral(numeroDia);

                    if (esDiaLaboral) {
                        System.out.println("Es un día laboral.\n");
                    } else {
                        System.out.println("No es un día laboral.\n");
                    }
                    break;
                case 2:
                    System.out.print("Ingrese un número entero entre 33 y 255 inclusive: ");
                    int codigoAscii = guti.nextInt();

                    if (codigoAscii >= 33 && codigoAscii <= 255) {
                        char caracterAscii = (char) codigoAscii;
                        System.out.println(codigoAscii + " corresponde a " + caracterAscii + "\n");
                    } else {
                        System.out.println("El número no corresponde a un código ASCII válido.\n");
                    }
                    break;
                case 3:
                    System.out.print("Ingrese un número entero positivo: ");
                    int numeroMultiplicar = guti.nextInt();

                    if (numeroMultiplicar >= 0) {
                        System.out.println("La tabla de multiplicar del número " + numeroMultiplicar + " es:");
                        for (int i = 1; i <= 15; i++) {
                            System.out.println(numeroMultiplicar + " * " + i + " = " + (numeroMultiplicar * i));
                        }
                    } else {
                        System.out.println("Por favor, ingrese un número entero positivo.\n");
                    }
                    break;
                case 4:
                    System.out.println("Saliendo del programa, NOS VEMOS GENTE");
                    break;
                default:
                    System.out.println("Opción no válida. Por favor, elija una opción del 1 al 4.\n");
                    break;
            }
        }
    }

    
    
    
    
    
    // Función para determinar si un día es laboral o no
    private static boolean esDiaLaboral(int dia) {
        // Se considera que los días laborales son desde lunes (1) hasta viernes (5)
        return dia >= 1 && dia <= 5;
    }
}
