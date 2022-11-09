---
title: "Cow Signal"
enableToc: false
date: 2022-11-09
tags:
- USACO
- Bronze
- CP
---

USACO 2016 December Contest, Bronze - Problem 3. The Cow-Signal
# Problem Statement

Bessie and her cow friends are playing as their favorite cow superheroes. Of course, everyone knows that any self-respecting superhero needs a signal to call them to action. Bessie has drawn a special signal on a sheet of $M×N$ paper $(1≤M≤10,1≤N≤10)$, but this is too small, much too small! Bessie wants to amplify the signal so it is exactly $K$ times bigger $(1≤K≤10)$ in each direction.

#### Input Format (cowsignal.in)

The first line of input contains $M$,$N$, and $K$, separated by spaces.
The next $M$ lines each contain a length-$N$ string, collectively describing the picture of the signal.

#### Output Format (cowsignal.out)

You should output $KM$ lines, each with $KN$ characters, giving a picture of the enlarged signal.


#### Sample Input: 
5 4 2   <br>
XXX.    <br>
X..X    <br>
XXX.    <br>
X..X    <br>
XXX.    <br>
#### Sample Output:

XXXXXX..    <br>
XXXXXX..    <br>
XX....XX    <br>
XX....XX    <br>
XXXXXX..    <br>
XXXXXX..    <br>
XX....XX    <br>
XX....XX    <br>
XXXXXX..    <br>
XXXXXX..    <br>

# My Solution
<br>

```
#include <iostream>
#include <vector>
#include <string>
using namespace std;

int main()
{
    freopen("cowsignal.in", "r", stdin);
	freopen("cowsignal.out", "w", stdout);
    int m,n,k;
    scanf("%d %d %d", &m, &n, &k);
    string s; 
    vector<string> signal;
    for(int i = 0; i < m; i++){
        cin >> s;
        string newSignal = "";

        for(int j = 0; j < n; j++){
            for(int x = 0; x < k; x++){
                newSignal.push_back(s[j]);
            }
        }
        for(int y = 0; y < k; y++){
            signal.push_back(newSignal);
        }
    }
    for(string s: signal){
        cout << s << endl;
    }
    return 0;
}

```
