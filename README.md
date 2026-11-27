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
    public boolean canAliceWin(int n) {
        return (0x61F03F807FC00L >> n & 1) == 1;
    }
}

priyamshree/helloworld

class Solution {
    public int maximumSaleItems(int[][] items, int budget) {
        int[] factors = Arrays.stream(items).mapToInt(item -> item[0]).toArray();
        int[] prices = Arrays.stream(items).mapToInt(item -> item[1]).toArray();
        int top = Arrays.stream(factors).max().getAsInt();
        int[] have = new int[top + 1], gains = new int[top + 1];  // have[f]: items with factor f
        for (int factor : factors) have[factor]++;
        for (int factor = 1; factor <= top; factor++)
            for (int multiple = factor; multiple <= top; multiple += factor)  // every factor-th cell is a multiple
                gains[factor] += have[multiple];

        int cheapest = Arrays.stream(prices).min().getAsInt();
        int[] best = new int[budget + 1];  // no first copies yet: everything goes to the cheapest item
        Arrays.setAll(best, money -> money / cheapest);
        for (int[] item : items) {
            int factor = item[0], price = item[1], gain = gains[factor];
            if (gain > price / cheapest)  // else the same money buys as many copies of the cheapest item
                for (int money = budget; money >= price; money--)  // backwards: one first copy per item
                    best[money] = Math.max(best[money], best[money - price] + gain);
        }
        return best[budget];
    }
}
