# aug06_2025
The problem that i solved today

Given a string s in Roman number format, your task is to convert it to an integer. Various symbols and their values are given below.
Note: I = 1, V = 5, X = 10, L = 50, C = 100, D = 500, M = 1000

Code:
class Solution {
    public int romanToDecimal(String s) {
        Map<Character,Integer> m=new HashMap<>();
        m.put('I',1);
        m.put('V',5);
        m.put('X',10);
        m.put('L',50);
        m.put('C',100);
        m.put('D',500);
        m.put('M',1000);
        int num=m.get(s.charAt(s.length()-1));
        for(int i=s.length()-2;i>=0;i--)
        {
            if(m.get(s.charAt(i+1))>m.get(s.charAt(i)))
                num-=m.get(s.charAt(i));
            else
                num+=m.get(s.charAt(i));
        }
        return num;
    }
}
