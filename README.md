# assignment2-Devarapalli
My second repository for Lab2

# saibabu Devarapalli
###### McDonald's Hyderabad
McDonals's located in **Forum Mall** and the famous place near to mall is **Art Gallery** , it is a building for the exhibition of art, usually visual art.

---

# Way to Mall
# Hyderabad International Airport
 * Book a cab
 * reach the destination
 * The destination there is a  Art Gallery
 * next building is Forum Mall

 # Unordered List
 * Go to McDonald's
    * Order the food
    * Chicken Burger
    * Coco-cola
    * french fries
 *Enjoy the food

# using aboutme link

[Google](https://github.com/saibabu369/assignment2-Devarapalli/blob/main/AboutMe.md)    

---

# Creating a sports

| sports | location | payment |
| --- | --- | ---: |
| reck | reck hub | 10 |
| nba | nba stand | 20 |
| tennis | court hub | 30 |

---
# using pithy quotes

> the purpose of our life is to be happy

*Lama*

> be the change you want to see in the world

*Gandhi*

---

# creating fencing code

> the branch of mathematics dealing with combinations of objects belonging to a finite set in accordance with certain constraints, such as those of graph theory.

 <https://www.google.com/search?q=combinatorics+definition&rlz=1C1GCEA_enUS988US988&oq=Combinatorics+definat&aqs=chrome.1.69i57j0i13j0i13i30l4j0i10i22i30j0i5i13i30l2j0i8i13i30.5541j0j15&sourceid=chrome&ie=UTF-8>

Divide and Conquer DP

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


 <https://cp-algorithms.com/dynamic_programming/divide-and-conquer-dp.html>



