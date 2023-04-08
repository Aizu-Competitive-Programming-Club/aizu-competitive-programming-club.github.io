# プログラミングを体験してみよう - src
https://aizu-competitive-programming-club.github.io/#/beginner/

### A1-1 (0315) - 参加者数
```cpp
#include <iostream>

int main() {
    int p, m, c;
    std::cin >> p >> m >> c;

    std::cout << p + m + c << std::endl;
}
```

### A1-2 (0479) - ２０周年
```cpp
#include <iostream>

int main() {
  int Y;
  std::cin >> Y;

  std::cout << Y - 2002 << std::endl;
}
```

### A1-3 (0335) - ワード
```cpp
#include <iostream>

int main() {
  int W;
  std::cin >> W;

  std::cout << 32 * W << std::endl;
}
```

### A1-4 (0453) - マウス の移動距離
```cpp
#include <iostream>

int main() {
    int d;
    std::cin >> d;

    std::cout << d / 4 << std::endl;
}
```

### A1-5 (0357) - お年玉
```cpp
#include <iostream>

int main() {
  int a, b;
  std::cin >> a >> b;

  std::cout << (a + b) / 2 << std::endl;
}
```

### B1-1 (4000) - 卓球
```cpp
#include <iostream>

int main() {
  int p, q;
  std::cin >> p >> q;

  if ((p + q) % 6 == 0) {
    std::cout << 1 << std::endl;
  } else {
    std::cout << 0 << std::endl;
  }
}
```

### B1-2 (0405) - アスキー文字
```cpp
#include <iostream>

int main() {
  int N;
  std::cin >> N;

  if (65 <= N and N <= 90) {
    std::cout << 1 << std::endl;
  } else if (97 <= N and N <= 122) {
    std::cout << 2 << std::endl;
  } else {
    std::cout << 0 << std::endl;
  }
}
```

### B1-3 (0358) - 買い物
```cpp
#include <iostream>

int main() {
  int m, f, b;
  std::cin >> m >> f >> b;

  if (b <= m) {
    std::cout << 0 << std::endl;
  }

  if (b > m and b <= m + f) {
    std::cout << b - m << std::endl;
  }

  if (b > m + f) {
    std::cout << "NA" << std::endl;
  }
}
```

### B1-4 (0429) - 商店街へのお出かけ
```cpp
#include <iostream>

int main() {
  int w, m, s;
  std::cin >> w >> m >> s;

  if (m < s and m < (w - s)) {
    std::cout << 0 << std::endl;
  } else if (m >= s and m < (w - s)) {
    std::cout << 1 << std::endl;
  } else if (m < s and m >= (w - s)) {
    std::cout << 2 << std::endl;
  } else {
    std::cout << 3 << std::endl;
  }
}
```

### B1-5 (0257) - 乗車券
```cpp
#include <iostream>

int main() {
  int b1, b2, b3;
  std::cin >> b1 >> b2 >> b3;

  if ((b1 == 1 and b2 == 1 and b3 == 0) or (b1 == 0 and b2 == 0 and b3 == 1)) {
    std::cout << "Open" << std::endl;
  } else {
    std::cout << "Close" << std::endl;
  }
}
```

### C1-1 (0406) - ２の累乗
```cpp
#include <iostream>

int main() {
  int N;
  std::cin >> N;

  int answer = 1;
  while (2 * answer <= N) {
    answer = 2 * answer;
  }

  std::cout << answer << std::endl;
}
```

### C1-2 (0455) - ダイヤル錠
```cpp
#include <iostream>

int main() {
  int N;
  std::cin >> N;

  int prev_a = 0;
  int answer = 0;

  for (int i = 0; i < N; i++) {
    int a;
    std::cin >> a;

    int ccw, cw;
    if (prev_a <= a) {
      ccw = a - prev_a;
      cw = (10 + prev_a) - a;
    } else {
      cw = prev_a - a;
      ccw = (10 + a) - prev_a;
    }

    if (ccw < cw) {
      answer += ccw;
    } else {
      answer += cw;
    }

    prev_a = a;
  }

  std::cout << answer << std::endl;
}
```

### C1-3 (0431) - カラフル円盤通し
```cpp
#include <iostream>
#include <vector>

int main() {
  int N;
  std::cin >> N;

  std::vector< int > r(N);
  for (int i = 0; i < N; i++) {
    std::cin >> r[i];
  }

  int max_r = 0;
  int answer = 0;
  for (int i = N - 1; i >= 0; i--) {
    if (max_r < r[i]) {
      answer++;
      max_r = r[i];
    }
  }

  std::cout << answer << std::endl;
}
```

### C1-4 (0407) - 集会所
```cpp
#include <iostream>
#include <vector>

int main() {
  int N;
  std::cin >> N;

  std::vector< int > x(N);
  for (int i = 0; i < N; i++) {
    std::cin >> x[i];
  }

  int min_x = 2000, max_x = 0;
  for (int i = 0; i < N; i++) {
    if (min_x > x[i]) {
      min_x = x[i];
    }
    if (max_x < x[i]) {
      max_x = x[i];
    }
  }

  std::cout << (max_x - min_x + 1) / 2 << std::endl;
}
```

### C1-5 (0318) - 極秘調査
```cpp
#include <iostream>
#include <vector>

int main() {
  int N;
  std::cin >> N;

  int X;
  std::cin >> X;

  std::vector< int > a(X);
  for (int i = 0; i < X; i++) {
    std::cin >> a[i];
  }

  int Y;
  std::cin >> Y;

  std::vector< int > b(Y);
  for (int i = 0; i < Y; i++) {
    std::cin >> b[i];
  }

  int Z;
  std::cin >> Z;

  std::vector< int > c(Z);
  for (int i = 0; i < Z; i++) {
    std::cin >> c[i];
  }

  int answer = 0;
  for (int i = 0; i < Z; i++) {
    int is_belongs_a = 0;
    for (int j = 0; j < X; j++) {
      if (a[j] == c[i]) {
        is_belongs_a = 1;
      }
    }

    int is_belongs_b = 0;
    for (int j = 0; j < Y; j++) {
      if (b[j] == c[i]) {
        is_belongs_b = 1;
      }
    }

    if (is_belongs_a == 0 or is_belongs_b == 1) {
      answer++;
    }
  }

  std::cout << answer << std::endl;
}
```

