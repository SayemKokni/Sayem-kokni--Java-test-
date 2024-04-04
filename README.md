# Sayem-kokni--Java-test-
Q.1 ) 
import java.util.Arrays;

public class MergeArrays {
   public static void mergeArrays(int[] X, int[] Y) {
        int m = X.length;
        int n = Y.length;
        int k = m - 1;
        for (int i = m - 1; i >= 0; i--) {
            if (X[i] != 0) {
                X[k] = X[i];
                k--;
            }
        }
        int i = k + 1; 
        int j = 0;     
        int p = 0;     
        
        while (i < m && j < n) {
            if (X[i] < Y[j]) {
                X[p] = X[i];
                i++;
            } else {
                X[p] = Y[j];
                j++;
            }
            p++;
        }
        
        while (j < n) {
            X[p] = Y[j];
            j++;
            p++;
        }
    }

    public static void main(String[] args) {
        int[] X = { 0, 2, 0, 3, 0, 5, 6, 0, 0 };
        int[] Y = { 1, 8, 9, 10, 15 };
        
        mergeArrays(X, Y);
        
        System.out.println("Merged Array: " + Arrays.toString(X));
    }
}

------------------—------------------------------------------

Q.2) 
public class MaximumSumPath {
    public static int maxSumPath(int[] X, int[] Y) {
        int m = X.length;
        int n = Y.length;
        
        int i = 0, j = 0;
        int sumX = 0, sumY = 0, result = 0;
        
        while (i < m && j < n) {
            if (X[i] < Y[j]) {
                sumX += X[i++];
            } else if (X[i] > Y[j]) {
                sumY += Y[j++];
            } else { // X[i] == Y[j]
                result += Math.max(sumX, sumY) + X[i];
                sumX = 0;
                sumY = 0;
                i++;
                j++;
            }
        }
        
        while (i < m) {
            sumX += X[i++];
        }
        
        while (j < n) {
            sumY += Y[j++];
        }
        
        result += Math.max(sumX, sumY);
        
        return result;
    }

    public static void main(String[] args) {
        int[] X = { 3, 6, 7, 8, 10, 12, 15, 18, 100 };
        int[] Y = { 1, 2, 3, 5, 7, 9, 10, 11, 15, 16, 18, 25, 50 };
        
        int maxSum = maxSumPath(X, Y);
        
        System.out.println("Maximum sum path: " + maxSum);
    }
}

------------------------------------------------------------

Q.3) 

import java.util.HashMap;

public class WordCount {
    public static void main(String[] args) {
        String input = "This is a sample string with some words. “
        input = input.replaceAll("[^a-zA-Z ]", "").toLowerCase();
        String[] words = input.split("\\s+");
        HashMap<String, Integer> wordCountMap = new HashMap<>();
        for (String word : words) {
            if (wordCountMap.containsKey(word)) {
               
                wordCountMap.put(word, wordCountMap.get(word) + 1);
            } else {
                wordCountMap.put(word, 1);
            }
        }

       
        System.out.println("Word Counts:");
        for (String word : wordCountMap.keySet()) {
            System.out.println(word + ": " + wordCountMap.get(word));
        }
        int totalWords = words.length;
        System.out.println("Total number of words: " + totalWords);
    }
}

--------------------------------------------------------------------

Q.4)
    public static void main(String[] args) {
        int[] X = { 0, 2, 0, 3, 0, 5, 6, 0, 0 };
        int[] Y = { 1, 8, 9, 10, 15 };
        
        mergeArrays(X, Y);
        
        System.out.println("Merged Array: " + Arrays.toString(X));
    }
}
public class DuplicateCharacters { 
public static void main(String[] args) { 
String string1 = "Great responsibility";  
int count;             
char string[] = string1.toCharArray();  
System.out.println("Duplicate characters in a given string: ");  
for(int i = 0; i <string.length; i++) {  
count = 1; 
for(int j = i+1; j <string.length; j++) {  
if(string[i] == string[j] && string[i] != ' ') {  
count++;  
string[j] = '0';  
}  
} 
if(count > 1 && string[i] != '0')  
System.out.println(string[i]); 
}  
}  
}  


