# password
## Judge Password is strong or not
CSDN text

编写一个函数，接收一个字符串作为参数，判断该字符串作为密码的话其安全强度如何。
如果字符串中只包含大写字母、小写字母、数字字符或标点符号中的一种则为弱密码，包含两种为中低安全密码，包含三种为中高安全密码，包含四种则为强密码。
(额外要求：不可以使用正则表达式)

```
from string import ascii_lowercase, ascii_uppercase, digits, punctuation

def Strength(password):
    PsdList = [ascii_lowercase, ascii_uppercase, digits, punctuation]
    L = [0, 0, 0, 0]
    for p in password:
        if p in PsdList[0]:
            L[0] += 1
        elif p in PsdList[1]:
            L[1] += 1
        elif p in PsdList[2]:
            L[2] += 1
        elif p in PsdList[3]:
            L[3] += 1
        else:
            pass

    count = L.count(0)
    if count == 4:
        print("InvalidPassword")
    elif count == 3:
        print("low")
    elif count == 2:
        print("middlelow")
    elif count == 1:
        print("middlehigh")
    else:
        print("high")

if __name__ == '__main__':
    print(Strength(""))
 ```
