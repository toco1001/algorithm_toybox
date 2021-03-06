プログラムの説明

![](https://i.gyazo.com/dbab8df0272fc74bbae3d146f95cb70a.png)

![](https://i.gyazo.com/ee412b5845edc868f4c8b7a7e55a3c39.png)

# 設問 プログラム中の[FillMe: x]に入れる正しい答えを、解答群の中から選べ。

aに関する解答群
- ア invtype == 1
- イ invtype == 2
- ウ invtype == 3
- エ invtype == 4
- オ (invtype == 1) || (invtype == 2)
- カ (invtype == 3) || (invtype == 4)

b, cに関する解答群
- ア in[RSZ - i - 1][j]
- イ in[RSZ - j - 1][i]
- ウ in[i][CSZ - j - 1]
- エ in[i][RSZ - j - 1]
- オ in[j][CSZ - i - 1]
- カ in[j][RSZ - i - 1]

```
#include <stdio.h>
#define RSZ 6
#define CSZ 8

void invert(int invtype, char in[CSZ][RSZ]) {
  int row = RSZ, col = CSZ;
  int i, j;

  if ([FillMe: a]) {
    row = CSZ;
    col = RSZ;
  }
  for (int i = 0; i < col; i++) {
    for (int j = 0; j < row; j++) {
      switch (invtype) {
        case 1: /* 90度右回転 */
          printf("%c", in[CSZ - j - 1][i]);
          break;
        case 2: /* 90度左回転 */
          printf("%c", [FillMe: b]);
          break;
        case 3: /* 上下反転 */
          printf("%c", in[CSZ - i - 1][j]);
          break;
        case 4: /* 左右反転 */
          printf("%c", [FillMe: c]);
          break;
        default:
          break;
      }
    }
    printf("\n");
  }
}

int main(int argc, char const *argv[]) {
  char src[CSZ][RSZ] = {{'#', '#', '#', '#', '#', '#'},
                        {'#', ' ', ' ', ' ', ' ', ' '},
                        {'#', ' ', ' ', ' ', ' ', ' '},
                        {'#', ' ', ' ', ' ', ' ', ' '},
                        {'#', '#', '#', ' ', ' ', ' '},
                        {'#', ' ', ' ', ' ', ' ', ' '},
                        {'#', ' ', ' ', ' ', ' ', ' '},
                        {'#', ' ', ' ', ' ', ' ', ' '}};
  invert(1, src);
  invert(2, src);
  invert(3, src);
  invert(4, src);
  return 0;
}
```
