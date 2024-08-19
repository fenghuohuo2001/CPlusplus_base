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

# 4. A+B问题IV 
[题目链接](https://kamacoder.com/problempage.php?pid=1003) 

```CPP
#include<iostream>
using namespace std;
int main(){
    int n, a;
    while (cin >> n) {
        if (n == 0) break;
        int sum = 0;
        while (n--) {
            cin >> a;
            sum += a;
        }
        cout << sum << endl;
    }
}
```

错误案例分析：
```cpp
#include <iostream>
using namespace std;

int main(){
    int N;
    int input;
    while(cin >> N){
        if(N == 0) break;
        int sum = 0;
        while(N--){
            while(cin >> input) sum += input;    // ××××××××
        }
        cout << sum << endl;
    }
}
```
上述代码中，使用while接收input的输入，是不合理的。
因为cin后面跟随几个变量，就会接收几个输入，多余的输入会丢失。
例如以下代码：
```cpp
#include <iostream>
using namespace std;

int main(){
    int a;
    cin >> a;
    cout << a << endl;
}
```
```
---------------------
输入： 1 2 3 4 5 6
输出： 1
---------------------
输入：3 4
输出：3
---------------------
```

# 5. A+B问题VII 
[题目链接](https://kamacoder.com/problempage.php?pid=1004) 

```CPP
#include<iostream>
using namespace std;
int main() {
    int a, b;
    while (cin >> a >> b) cout << a + b << endl << endl;
}
```

# 6. A+B问题VIII （ac）
[题目链接](https://kamacoder.com/problempage.php?pid=1005)

```CPP 
#include<iostream>
using namespace std;
int main() {
    int n, a, b;
    while (cin >> n) {
        while (n--) {
            cin >> a;
            int sum = 0;
            while (a--) {
                cin >> b;
                sum += b;
            }
            cout << sum << endl;
            if (n != 0) cout << endl;
        }
    }
}
```

# 7.平均绩点 （注意代码格式， 如： if中的 “;” 位置）
[题目链接](https://kamacoder.com/problempage.php?pid=1006)

```CPP
#include <iostream>
#include <stdio.h>
using namespace std;
int main() {
    string s;
    // int flag = 1;     // 若将flag定义在这里，则每行不会重置flag的值。
    while (getline(cin, s)) { // 接受一整行字符串
        float sum = 0;
        int count = 0;
        int flag = 1;
        for (int i = 0; i < s.size(); i++) {
            if (s[i] == 'A') {sum += 4; count++;}
            else if (s[i] == 'B') {sum += 3; count++;}
            else if (s[i] == 'C') {sum += 2; count++;}
            else if (s[i] == 'D') {sum += 1; count++;}
            else if (s[i] == 'F') {sum += 0; count++;}
            else if (s[i] == ' ') continue;
            else {
                flag = 0;
                cout << "Unknown" << endl;
                break;
            }
        }
        if (flag) printf("%.2f\n", sum / count);
    }
    return 0;
}
```

# 8. 摆平积木 
[题目链接](https://kamacoder.com/problempage.php?pid=1007) 

```CPP 
#include<iostream>
#include<vector>
using namespace std;

int main() {
    int n;
    while (cin >> n) {
        if (n == 0) break;
        vector<int> nums = vector<int>(n, 0);
        int sum = 0;
        for (int i = 0; i < n; i++) {
            cin >> nums[i];
            sum += nums[i];
        }
        int average = sum / n;
        int result = 0;
        // 这一段写法有两种
        // ------------写法1------------
        for (int i = 0; i < n; i++) {
            if ((nums[i] - average) > 0) result += (nums[i] - average);
        }
        // -----------------------------
        /*
        // ------------写法2------------
        for(int num: nums){
            if(num > avg) result += num - avg;
        }
        */
        // -----------------------------
        cout << result << endl;
        cout<< endl;
    }
}
```

# 9. 奇怪的信
[题目链接](https://kamacoder.com/problempage.php?pid=1008)

```CPP
#include<iostream>
using namespace std;
int main() {
    int n, a;
    while (cin >> n) {
        int result = 0;
        while (n != 0) {
            a = (n % 10);
            n = n / 10;
            if (a % 2 == 0) result += a;
        }
        cout << result << endl;
        cout << endl;
    }
}
```






















