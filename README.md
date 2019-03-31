/*
 * To change this license header, choose License Headers in Project Properties.
 * To change this template file, choose Tools | Templates
 * and open the template in the editor.
 */
package ergasia5;

/**
 *
 * @author lampz
 */
public class TicTacToe 
{   
    int i,j;
    private final String[][] a;
    private static final int ROWS = 3;
    private static final int COLS = 3;
    private final String x = "\\s{3}";

public TicTacToe()
{
  a = new String[ROWS][COLS];
}

//Arxikopoihsh pinaka
public void Arxk_a() 
{
    for (i=0; i<ROWS; i++)
    {
        for (j=0; j<COLS; j++)
        {
            a[i][j] = " ";
            
        }
    }
}
    public void b(int i, int j, String paixnidi)
    {
       if(this.a[i][j].matches(x)); 
       a[i][j] = "+paixnidi+";
    }
  
    public boolean termat_paixnd()
    {   //elegxoume prwta tis grammes
        for(i=0; i< ROWS; i++)
        {
            if (a[i][0].matches(x) && a[i][0].equals(a[i][1]) && a[i][1].equals(a[i][2]))
            {
                return true;
            }
        }
        //elegxoume meta tis sthles
        for (j=0; j<COLS; j++)
      {        
            if (a[0][0].matches(x) && a[0][j].equals(a[1][j]) && a[1][j].equals(a[2][j]))
            {
                return true;
            }
        //elegxoume tis diagwnies 
        if(a[0][0].matches(x) && a[0][0].equals(a[1][1])&& a[1][1].equals(a[2][2]))
        {
            return true;
        }
        if (a[0][2].matches(x) && a[0][2].equals(a[1][1]) && a[1][1].equals(a[2][0]))
        {
            return true;
        }
       }  
        // kanenas den nikaei 
        return false;
    }
  /*
   Ektypwsh pinaka
    Epistrefei ton board
  */
   public String ektps_a()
   {
       String board = "";
       for (i=0; i<ROWS; i++)
       {
           for (j=0; j<COLS; j++)
           {
               if(j!=COLS-1)
                  board += a[i][j] + "X";
               else 
                  board += a[i][j];
            }
           if (i!=COLS-1)
            board += "\n---+---+---\n";
       }
      return board; 
   }
}

//Epomeno file
 
/*
 * To change this license header, choose License Headers in Project Properties.
 * To change this template file, choose Tools | Templates
 * and open the template in the editor.
 */
package ergasia5;

import java.util.Scanner;

/**
 *
 * @author lampz
 */

public class TicTacToe1 
{
    public static void main (String[] args)
    {  
        Scanner input = new Scanner(System.in); //eisagwgh stoixeiwn
        TicTacToe game = new TicTacToe();  
        paixnidi.Arxk_a();
        String symvl="X";
        do
        {
            System.out.println(paixnidi.ektps_a());
            System.out.println("Dwse xarakthra gia tis grammes");
            int ROW = input.nextInt();
            System.out.println("Dwse xarakthra gia tis sthles");
            int COL = input.nextInt();
            paixnidi.setPlay(ROW, COL, symvl);
            if(paixnidi.termat_paixnd())
            {
                System.out.println(paixnidi.ektps_a() + "\n" + symvl +  "nikhths");
                break;
            }
                if (symvl=="X")
                    symvl = "O";
                else 
                    symvl = "X";
                
        }
         while(true);
    }
}
