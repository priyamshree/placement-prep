# placement-prep

## Preparation for placement.
- Leetcode
- GeeksForGeeks
- Codechef
- A2Z Sheet
- SQL 30+ hour video lecture
- Java by apna college
- sql by wscube tech for basic - intermediate. good for beginners
- Operating Systems
- Database Management Systems
- Machine Learning
- Deep Learning
- Artificial Intelligence
- Natural Language Processing

```
contact me
email: priyam1953shree@gmail.com
```
hello
this is a placement prep testing, site where we can come and get resources. this is a data science and ai era.




class Solution {
    public char posInfinite(String s, int pos) {
        long len = s.length();
        long p = pos;

        while (len < p) {
            len = 2 * len + 1;
        }

        while (p > s.length()) {
            long oldLen = (len - 1) / 2;

            if (p == oldLen + 1) {
                return '$';
            }

            if (p > oldLen + 1) {
                p = len - p + 1;
            }

            len = oldLen;
        }

        return s.charAt((int) p - 1);
    }
}
