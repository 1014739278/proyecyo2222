# proyecyo2222
prg
import java.util.Random;
import java.util.Scanner;

public class NumeroInteligente {
    // Función para contar los factores de un número
    public static int contarFactores(int num) {
        int count = 0;
        for (int i = 1; i <= num; i++) {
            if (num % i == 0) {
                count++;
            }
        }
        return count;
    }

    // Función para determinar si un número es inteligente
    public static boolean esInteligente(int num) {
        return contarFactores(num) % 2 != 0;
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        Random random = new Random();

        // Solicitar la cantidad de números a validar
        System.out.print("Ingrese la cantidad de números a validar: ");
        int cantidad = scanner.nextInt();

        // Generar y procesar los números
        int[] numeros = new int[cantidad];
        for (int i = 0; i < cantidad; i++) {
            numeros[i] = random.nextInt(100) + 1; // Números entre 1 y 100
        }

        // Mostrar los números generados
        System.out.print("Números generados: ");
        for (int i = 0; i < cantidad; i++) {
            System.out.print(numeros[i]);
            if (i < cantidad - 1) {
                System.out.print(", ");
            }
        }
        System.out.println();

        // Evaluar si cada número es inteligente
        for (int num : numeros) {
            System.out.println(num + ": " + (esInteligente(num) ? "Sí" : "No"));
        }

        scanner.close();
    }
}
