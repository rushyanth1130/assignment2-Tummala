# assignment2-Tummala
This is assignment 2 of web apps markdown
# Nagarushyanth Tummala 
###### Sydney ######
**Sydney is famous for its beaches.** Mostly Bondi Beach but there are so many other great (better in my opinion) beaches scattered all along this coastal city and **with Sydney’s perfect climate it is warm enough to be visiting the beaches about eight months of the year.** A large amount of my life has been spent on the beaches of Sydney.

*******
## Directions from Maryville to Sydney

1. From Maryville take a ride to Kansas City International airport (MCI).
    1. Ask friends to get a ride to airport.
2. From the airport, take a flight to (Kingsford Smith International Airport).
    1. Prefer American Airlines, United, Delta Airways and need a tourist visa.
3. From the airport take a bus to Bondi beach.
    1. Take route 333N bus.
    2. There might be chances of using multiple route buses.
4. After reaching there, one can a have beautiful view of beach and ocean.
    1. There are other areas in Sydney to visit, one of which is Watson Bay. 
    2. One can have a panaromic view of the ocean with curises ships and Blue Whales. 
*******
### Items to be brought for enjoyment
* Mats
+ Water
- Speaker
* Sunscreen
+ Food
* Surfing Boards
- Sunglasses
* Towels <br />
<hr />
[AboutMe description link](https://github.com/rushyanth1130/assignment2-Tummala/blob/main/AboutMe.md)

<hr />

## Table for my food and beverages ##

This section has my favorite food, drink and the location where I would like to get those.

| Food/Drink             | Location  | Amount |
| ---------------------- | --------- | ------ |
| Spicy Chicken Sandwich | IHOP      | $8     |
| Pizza                  | Pizza hut | $20    |
| Burito Bowl            | TAcoBell  | $8     |
| Sprite                 | Walmart   | $4     |

<hr />

### Pithy Quotes ###
> Be curious, not judgmental.<br />
_~Walt Whitman_<br />
> Everything comes in time to him who knows how to wait. <br />
_~Leo Tolstoy_<br />

<hr />

### Code Fencing ###
> Usually, the monotone property is find either by instinct, print out the DP table, or by Monge condition. 
> Actually, divide and conquer optimization is a special case of 1D/1D convex/concave Knuth optimization(cost function doesn't depends on previous DP values).
[Description Link](https://robert1003.github.io/2020/02/25/dp-opt-divide-and-conquer.html)

```
int m, n;
vector<long long> dp_before(n), dp_cur(n);

long long C(int i, int j);

// compute dp_cur[l], ... dp_cur[r] (inclusive)
void compute(int l, int r, int optl, int optr) {
    if (l > r)
        return;

    int mid = (l + r) >> 1;
    pair<long long, int> best = {LLONG_MAX, -1};

    for (int k = optl; k <= min(mid, optr); k++) {
        best = min(best, {(k ? dp_before[k - 1] : 0) + C(k, mid), k});
    }

    dp_cur[mid] = best.first;
    int opt = best.second;

    compute(l, mid - 1, optl, opt);
    compute(mid + 1, r, opt, optr);
}

int solve() {
    for (int i = 0; i < n; i++)
        dp_before[i] = C(0, i);

    for (int i = 1; i < m; i++) {
        compute(0, n - 1, 0, n - 1);
        dp_before = dp_cur;
    }

    return dp_before[n - 1];
}
```
[Algorithm Link](https://cp-algorithms.com/dynamic_programming/divide-and-conquer-dp.html)
