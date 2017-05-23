# First_repository
My first repository
package metodology_lab_5;

import java.util.Scanner;

public class Main {

	public static void main(String[] args) {
		// TODO Auto-generated method stub

		
		System.out.println("Введіть кількість невідомих");
		Scanner scan = new Scanner(System.in);
		int size = scan.nextInt();
		double [][] mass = new double [size][size];
		double[] result_mass = new double [size];
		double free [] = new double [size];
		System.out.println("Заповніть матрицю коефіцієнтів");
		for (int i = 0; i < mass.length; i++) {
			for (int j = 0; j < mass[i].length; j++) {
				mass[i][j] = scan.nextDouble();
			}
			System.out.println();
		}
		System.out.println("Заповніть вектор вільних членів");
		for (int i = 0; i < free.length; i++) {
			free[i] = scan.nextDouble();
		}
		scan.close();
		
		Gauss gus = new Gauss();
		gus.directMoving(mass, free);
		result_mass = gus.reverseMoving(mass, free);
		
		System.out.println("Результат :");
		for (int i = 0; i < result_mass.length; i++) {
			System.out.print(" " + result_mass[i]);
		}

	}

}

