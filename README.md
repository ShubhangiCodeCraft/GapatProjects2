# GapatProjects2
8010032706

Q1: Merge two arrays by satisfying given constraints
Given two sorted arrays X[] and Y[] of size m and n each where m >= n and X[] has exactly n vacant cells,
 merge elements of Y[] in their correct position in array X[], i.e., merge (X, Y) by keeping the sorted order.public class MergeArrays {

    public static void mergeArrays(int[] X, int[] Y) {
        int m = X.length;
        int n = Y.length;
        
        // Set pointers to the last non-vacant elements
        int i = n - 1;
        int j = n - 1;
        int k = m - 1;
        
        // Merge arrays
        while (i >= 0 && j >= 0) {
            if (X[i] > Y[j]) {
                X[k] = X[i];
                i--;
            } else {
                X[k] = Y[j];
                j--;
            }
            k--;
        }
        
        // If there are remaining elements in Y
        while (j >= 0) {
            X[k] = Y[j];
            j--;
            k--;
        }
    }

    public static void main(String[] args) {
        int[] X = {2, 3, 7, 0, 0, 0};  // Vacant cells are represented by 0s
        int[] Y = {1, 5, 6};
        
        mergeArrays(X, Y);
        
        // Print merged array X
        for (int num : X) {
            System.out.print(num + " ");
        }
    }
}
