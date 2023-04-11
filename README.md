# Matrix_Duplicate_Element_Put_Zero

package Com.nt.practice;

import java.util.Arrays;

/**
 * We create a boolean array called 'seen' to keep.
 * Track of which elements have been seen before.we loop through 
 * the matrix and replace any duplicate elements with 0.
 * after processing each row, we reset the 'seen' array 
 * so that we can use it for the next row.
 * 
 * @author 2232829
 *
 */
 
public class MatrixDuplicateElementPutZero {

	public static void main(String[] args) {
		int matrix[][] = new int[][] {
			{ 1, 1, 2, 2, 3, 4, 5 },
			{ 1, 1, 1, 1, 1, 1, 1 },
			{ 1, 2, 3, 4, 5, 6, 7 },
			{ 1, 2, 1, 1, 1, 1, 1 },
		};
   
		// Create a boolean array to keep track of arr elements.
		boolean[] arr=new boolean[10];
		//Loop through the matrix and replace duplicate elements with 0.
		for(int i=0;i<matrix.length;i++) {
			for(int j=0;j<matrix[i].length; j++) {
				int num=matrix[i][j];
				if(arr[num]) {
					matrix[i][j]=0;
				}
				else {
					arr[num]=true;
				}
			}
			// Reset the array array for the next row.
			Arrays.fill(arr, false);
		}
		//Print the matrix in the desired format.
		System.out.print("{");
		System.out.println();
		
		for(int i=0;i<matrix.length;i++) {
		 System.out.print("   {");
		  for(int j=0;j<matrix[i].length; j++) {
		    System.out.print(matrix[i][j]);
		     if(j<matrix[i].length-1) {
	                 System.out.print(",");
                      }
		}
		System.out.println("},");
	//	if(i<matrix.length-1) {
			//System.out.print(",");
		//}
		}
		System.out.print("};");
	}

Output:

{
   {1,0,2,0,3,4,5},
   
   {1,0,0,0,0,0,0},
   
   {1,2,3,4,5,6,7},
   
   {1,2,0,0,0,0,0},};

}
