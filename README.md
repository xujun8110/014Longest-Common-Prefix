# 014Longest-Common-Prefix
求一个字符串数组的最长公共前缀

找出最短字符串的长度，然后拿每一个字符比较

public class Solution {
    public String longestCommonPrefix(String[] strs) {
        
        if (strs == null) {
            return null;
        }

        if (strs.length == 0) {
            return "";
        }

        int min = Integer.MAX_VALUE;
        
        for(String str: strs){
            if(str == null){
                return null;
            }
            
            if(min > str.length())
                min = str.length();
        }
        
        boolean flag;
        int i;
        for(i = 0; i < min; i++){
            flag = true;
            for(int j = 1; j < strs.length; j++){
                if(strs[0].charAt(i) != strs[j].charAt(i)){
                    flag = false;
                    break;
                }
            }
            
            if(!flag)
                break;
            
        }
        
        return strs[0].substring(0, i);

        
    }
    
    
}
