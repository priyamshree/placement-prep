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

```

class Solution {
    public char posInfinite(String s, int pos) {
        long len = s.length();
        long p = pos;
        int step = 0;

        // Find the first construction whose length reaches pos
        while (len < p) {
            step++;
            len = 2 * len + step;
        }

        // Trace the position backwards
        for (int i = step; i >= 1; i--) {
            long prevLen = (len - i) / 2;

            // Position belongs to the newly appended '$' characters
            if (p > prevLen && p <= prevLen + i) {
                return '$';
            }

            // Position belongs to the reversed previous string
            if (p > prevLen + i) {
                p = len - p + 1;
            }

            len = prevLen;
        }

        return s.charAt((int) p - 1);
    }
}

```
