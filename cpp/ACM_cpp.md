# 1. A+B问题I 
[题目链接](https://kamacoder.com/problempage.php?pid=1000)

```CPP 
#include<iostream>
using namespace std;
int main() {
    int a, b;
    while (cin >> a >> b) cout << a + b << endl;
}
```

# 2.A+B问题II 
[题目链接](https://kamacoder.com/problempage.php?id=1001)

```CPP 
#include<iostream>
using namespace std;
int main() {
    int n, a, b;
    while (cin >> n) {
        while (n--) {
            cin >> a >> b;
            cout << a + b << endl;
        }
    }
}
```

# 3. A+B问题III 
[题目链接](https://kamacoder.com/problempage.php?pid=1002)

```CPP  
#include<iostream>
using namespace std;
int main() {
    int a, b;
    while (cin >> a >> b) {
        if (a == 0 && b == 0) break;
        cout << a + b << endl;
    }
}
```
