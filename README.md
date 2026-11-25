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
    static final long MOD = 1_000_000_007L;

    private long prefixSum(long x, int a, int b) {
        if (x <= 0) return 0;

        long c = a - b;
        long base = Math.min(x, a);

        long ans = base * (base + 1) / 2;

        if (x <= a) return ans;

        long k = (x - a) / c;

        // Sum of all complete movement cycles
        ans += c * (c * k * k + (2L * a + 1) * k) / 2;
        ans += (long) b * c * k * (k + 1);

        // Remaining incomplete cycle
        long nextK = k + 1;
        long left = k * c + a + 1;

        if (left <= x) {
            long count = x - left + 1;
            ans += (left + x) * count / 2;
            ans += 2L * b * nextK * count;
        }

        return ans;
    }

    public int minTime(int a, int b, int d, int l, int r) {
        long count = (long) r - l + 1;

        long upper = d - l;
        long lower = d - r - 1;

        long sum = count
                 + prefixSum(upper, a, b)
                 - prefixSum(lower, a, b);

        return (int) ((sum % MOD + MOD) % MOD);
    }
}
