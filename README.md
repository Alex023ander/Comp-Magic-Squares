# Comp-Magic-Squares

import java.util.Scanner;
    public class Square
        {
        int[][] square;
        int rowSum,colSum,daiSum,odaiSum;
        //--------------------------------------
        //create new square of given size
        //--------------------------------------
    public Square(int size)
    {
         square=new int[size][size];
    }

    //-----------------------------------------------
    //return the sum of the values in the given row
    //-----------------------------------------------
    public int sumRow(int row)
    {
        for (int col = 0; col < square.length; col ++)
                rowSum+=square[row-1][col];
        return rowSum;
    }
    //-------------------------------------------------
    //return the sum of the values in the given column
    //-------------------------------------------------
    public int sumCol(int col)
    {
        for (int row = 0; row < square.length; row ++)
                colSum+=square[row][col-1];
        return colSum;
    }
    //---------------------------------------------------
    //return the sum of the values in the main diagonal
    //---------------------------------------------------
    public int sumMainDiag()
    {
        int output=0;
        for (int x = 0; x < square.length; x ++)
                output+=square[x][x];
        daiSum=output;
        return output;
    }

    //---------------------------------------------------------------
    //return the sum of the values in the other (&quot;reverse&quot;) diagonal
    //---------------------------------------------------------------
    public int sumOtherDiag()
    {
       int output=0;
        for (int x = 0; x < square.length; x ++)
                output+=square[x][square.length-x-1];
        odaiSum=output;
        return output; 
    }
    //----------------------------------------------------------------
    //return true if the square is magic (all rows, cols, and diags
    //have same sum), false otherwise
    //----------------------------------------------------------------
    public boolean magic()
    {
        return rowSum==colSum&&daiSum==odaiSum&&colSum==daiSum;
    }
//----------------------------------------------------
//read info into the square from the input stream associated with
//the Scanner parameter
//----------------------------------------------------
public void readSquare(Scanner scan)
{
    for (int row = 0; row < square.length; row++)
        for (int col = 0; col < square.length; col ++)
            square[row][col] = scan.nextInt();

}
//---------------------------------------------------
//print the contents of the square, neatly formatted
//---------------------------------------------------
public void printSquare()
    {
    for (int row = 0; row < square.length; row++){
            System.out.println();
            for (int col = 0; col < square.length; col ++)
                System.out.print(square[row][col]+" ");
    }
    }
}
