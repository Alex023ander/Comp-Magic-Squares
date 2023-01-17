# Comp-Magic-Squares

import java.io.FileNotFoundException;
import java.io.File;
import java.util.Scanner;
public class Comp8MagicSquares {

    public static void main(String[] args) throws FileNotFoundException {
        Scanner scan = new Scanner(new File("D:\\AP CSA copy/AlexMagicSquares.txt"));
        
        int count = 1; //count which square we&#39;re on
        int size = scan.nextInt(); //size of next square
    
        //Expecting -1 at bottom of input file
        while (size != -1){
            //create a new Square of the given size
            Square square= new Square(size);
            //call its read method to read the values of the square
            square.readSquare(scan);
            System.out.println("\n******** Square " + count + " ********");
            square.printSquare();
            //print the square
            System.out.println(square.sumRow(size));
            //print the sums of its rows
            System.out.println(square.sumCol(size));
            //print the sums of its columns
            System.out.println(square.sumMainDiag());
            //print the sum of the main diagonal
            System.out.println(square.sumOtherDiag());
            //print the sum of the other diagonal
            System.out.println(square.magic());
            //determine and print whether it is a magic square
            //get size of next square
            count+=1;
            size = scan.nextInt();
        }
            
    }
    
}
