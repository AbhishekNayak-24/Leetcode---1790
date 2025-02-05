# Leetcode---1790
Check if One String Swap Can Make Strings Equal
//code in java
public class Solution {
    public boolean areAlmostEqual(String s1, String s2) {
        if (s1.equals(s2)) {
            return true;
        }

        int n = s1.length();
        char firstChar1 = ' ', firstChar2 = ' ';
        char secondChar1 = ' ', secondChar2 = ' ';
        int diffCount = 0;

        for (int i = 0; i < n; i++) {
            if (s1.charAt(i) != s2.charAt(i)) {
                diffCount++;
                if (diffCount == 1) {
                    firstChar1 = s1.charAt(i);
                    firstChar2 = s2.charAt(i);
                } else if (diffCount == 2) {
                    secondChar1 = s1.charAt(i);
                    secondChar2 = s2.charAt(i);
                } else {
                    return false;
                }
            }
        }

        return diffCount == 2 && firstChar1 == secondChar2 && firstChar2 == secondChar1;
    }

    public static void main(String[] args) {
        Solution solution = new Solution();
        System.out.println(solution.areAlmostEqual("bank", "kanb")); // Output: true
        System.out.println(solution.areAlmostEqual("attack", "defend")); // Output: false
        System.out.println(solution.areAlmostEqual("kelb", "kelb")); // Output: true
    }
}
