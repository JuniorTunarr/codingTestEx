# 5/29

## 문제:

평균 구하기

## 설명:

정수를 담고 있는 배열 arr의 평균값을 return하는 함수, solution을 완성해보세요.

## 입출력 예

|    arr    | return |
| :-------: | :----: |
| [1,2,3,4] |  2.5   |
|   [5,5]   |   5    |

## 답안:

```
function solution(arr) {
    return arr.reduce((a,c)=>a+c)/arr.length;
}
```

---

## 문제:

짝수와 홀수

## 설명:

정수 num이 짝수일 경우 "Even"을 반환하고 홀수인 경우 "Odd"를 반환하는 함수, solution을 완성해주세요.

## 입출력 예

| num | return |
| :-: | :----: |
|  3  | "Odd"  |
|  4  | "Even" |

## 답안:

```
function solution(num) {
    return num % 2 ===0 ? "Even" : "Odd";
}
```

---

## 문제:

자릿수 더하기

## 설명:

자연수 N이 주어지면, N의 각 자릿수의 합을 구해서 return 하는 solution 함수를 만들어 주세요.
예를들어 N = 123이면 1 + 2 + 3 = 6을 return 하면 됩니다.

## 입출력 예

|  N  | answer |
| :-: | :----: |
| 123 |   6    |
| 987 |   24   |

## 답안:

```

function solution(n){
return String(n).split("").reduce((a, c) => a + parseInt(c), 0)
}
```

---

# 5/30

## 문제:

약수의 합

## 설명:

정수 n을 입력받아 n의 약수를 모두 더한 값을 리턴하는 함수, solution을 완성해주세요.

## 입출력 예

|  N  | return |
| :-: | :----: |
| 12  |   28   |
|  5  |   6    |

## 답안:

```
function solution(n) {
    let sum = 0;

    for (let i = 1 ; i < n+1 ; i++){
        if(n % i ===0){
            sum += i
        }
    }
    return sum;
}
```

---

## 문제:

x만큼 간격이 있는 n개의 숫자

## 설명:

함수 solution은 정수 x와 자연수 n을 입력 받아, x부터 시작해 x씩 증가하는 숫자를 n개 지니는 리스트를 리턴해야 합니다. 다음 제한 조건을 보고, 조건을 만족하는 함수, solution을 완성해주세요.

## 입출력 예

|  x  |  n  |    return    |
| :-: | :-: | :----------: |
|  2  |  5  | [2,4,6,8,10] |
|  4  |  3  |   [4,8,12]   |
| -4  |  2  |   [-4, -8]   |

## 답안:

```

function solution(x, n) {
let answer = [];
for (let i = 1; i <= n; i++) {
    answer.push(x\*i)
}
    return answer;
}
```

---

## 문제:

나머지가 1이 되는 수 찾기

## 설명:

자연수 n이 매개변수로 주어집니다. n을 x로 나눈 나머지가 1이 되도록 하는 가장 작은 자연수 x를 return 하도록 solution 함수를 완성해주세요. 답이 항상 존재함은 증명될 수 있습니다.

## 입출력 예

|  N  | result |
| :-: | :----: |
| 10  |   3    |
| 12  |   11   |

## 답안:

```
function solution(n) {
  for (let i = 2; i < n; i++) {
    if (n % i === 1) return i;
  }
}
```

---

# 5/31

## 문제:

자연수 뒤집어 배열로 만들기

## 설명:

자연수 n을 뒤집어 각 자리 숫자를 원소로 가지는 배열 형태로 리턴해주세요. 예를들어 n이 12345이면 [5,4,3,2,1]을 리턴합니다.

## 입출력 예

|   N   |   return    |
| :---: | :---------: |
| 12345 | [5,4,3,2,1] |

## 답안:

```

function solution(n) {

    return n.toString().split("").reverse().map((v)=>Number(v));
```

}

## 문제:

문자열 내 p와 y의 개수

## 설명:

대문자와 소문자가 섞여있는 문자열 s가 주어집니다. s에 'p'의 개수와 'y'의 개수를 비교해 같으면 True, 다르면 False를 return 하는 solution를 완성하세요. 'p', 'y' 모두 하나도 없는 경우는 항상 True를 리턴합니다. 단, 개수를 비교할 때 대문자와 소문자는 구별하지 않습니다.

예를 들어 s가 "pPoooyY"면 true를 return하고 "Pyy"라면 false를 return합니다.

## 입출력 예

|     s     | answer |
| :-------: | :----: |
| "pPoooyY" |  true  |
|   "Pyy"   | false  |

## 답안:

```
function solution(s) {
  let pCount = s.split(/p/i).length - 1;
  let yCount = s.split(/y/i).length - 1;
  return pCount === yCount;
}
```

---

## 문제:

정수 제곱근 판별

## 설명:

임의의 양의 정수 n에 대해, n이 어떤 양의 정수 x의 제곱인지 아닌지 판단하려 합니다.
n이 양의 정수 x의 제곱이라면 x+1의 제곱을 리턴하고, n이 양의 정수 x의 제곱이 아니라면 -1을 리턴하는 함수를 완성하세요.

## 입출력 예

|  n  | return |
| :-: | :----: |
| 121 |  144   |
|  3  |   -1   |

## 답안:

```

function solution(n) {
let result = Math.sqrt(n)
return Number.isInteger(result) ? (result+1)\*(result+1) : -1 ;
}
```

---

# 6/1

## 문제:

문자열을 정수로 바꾸기

## 설명:

문자열 s를 숫자로 변환한 결과를 반환하는 함수, solution을 완성하세요.

## 입출력 예

예를 들어 str이 "1234"이면 1234를 반환하고, "-1234"이면 -1234를 반환하면 됩니다.
str은 부호(+,-)와 숫자로만 구성되어 있고, 잘못된 값이 입력되는 경우는 없습니다.

## 답안:

```
function solution(s) {
    return parseInt(s);
}
```

---

## 문제:

정수 내림차순으로 배치하기

## 설명:

함수 solution은 정수 n을 매개변수로 입력받습니다. n의 각 자릿수를 큰것부터 작은 순으로 정렬한 새로운 정수를 리턴해주세요. 예를들어 n이 118372면 873211을 리턴하면 됩니다.

## 입출력 예

|    n    | return |
| :-----: | :----: |
| 1118372 | 832111 |

## 답안:

```

function solution(n) {
return parseInt(n.toString().split("").sort((a,b)=>b-a).join(""))
}
```

---

## 문제:

하샤드 수

## 설명:

양의 정수 x가 하샤드 수이려면 x의 자릿수의 합으로 x가 나누어져야 합니다. 예를 들어 18의 자릿수 합은 1+8=9이고, 18은 9로 나누어 떨어지므로 18은 하샤드 수입니다. 자연수 x를 입력받아 x가 하샤드 수인지 아닌지 검사하는 함수, solution을 완성해주세요.

## 입출력 예

|  x  | return |
| :-: | :----: |
| 10  |  true  |
| 12  |  true  |
| 11  |  true  |
| 13  | false  |

## 답안:

```
function solution(x) { // x = 10
    let sum = 0;
    let arr = String(x).split(""); // [1,0]

    for(let i=0; i<arr.length; i++){
        sum += Number(arr[i]) // 1+0
    }
    return (x % sum == 0) ? true:false;
}
```

---

# 6/2

## 문제:

두 정수 사이의 합

## 설명:

두 정수 a, b가 주어졌을 때 a와 b 사이에 속한 모든 정수의 합을 리턴하는 함수, solution을 완성하세요.
예를 들어 a = 3, b = 5인 경우, 3 + 4 + 5 = 12이므로 12를 리턴합니다.

## 입출력 예

|  a  |  b  | return |
| :-: | :-: | :----: |
|  3  |  5  |   12   |
|  3  |  3  |   3    |
|  5  |  3  |   12   |

## 답안:

```

function solution(a, b) {
let answer = 0;
answer = (a+b) \* (Math.abs(b-a)+1)/2
return answer;
}
```

---

## 문제:

콜라츠 추측

## 설명:

1937년 Collatz란 사람에 의해 제기된 이 추측은, 주어진 수가 1이 될 때까지 다음 작업을 반복하면, 모든 수를 1로 만들 수 있다는 추측입니다. 작업은 다음과 같습니다.

1-1. 입력된 수가 짝수라면 2로 나눕니다.
1-2. 입력된 수가 홀수라면 3을 곱하고 1을 더합니다. 2. 결과로 나온 수에 같은 작업을 1이 될 때까지 반복합니다.
예를 들어, 주어진 수가 6이라면 6 → 3 → 10 → 5 → 16 → 8 → 4 → 2 → 1 이 되어 총 8번 만에 1이 됩니다. 위 작업을 몇 번이나 반복해야 하는지 반환하는 함수, solution을 완성해 주세요. 단, 주어진 수가 1인 경우에는 0을, 작업을 500번 반복할 때까지 1이 되지 않는다면 –1을 반환해 주세요.

## 입출력 예

|   n    | result |
| :----: | :----: |
|   6    |   8    |
|   16   |   4    |
| 626331 |   -1   |

## 답안:

```
function solution(num) {
    let count = 0;

    while (num != 1) {
        if (num % 2 == 0){
            num /= 2;
        } else {
            num = (num * 3) + 1;
        }
        count += 1;
    }
    if (count >= 500) {
        return -1;
    } else {
        return count;
    }
}
```

---

## 문제:

서울에서 김서방 찾기

## 설명:

String형 배열 seoul의 element중 "Kim"의 위치 x를 찾아, "김서방은 x에 있다"는 String을 반환하는 함수, solution을 완성하세요. seoul에 "Kim"은 오직 한 번만 나타나며 잘못된 값이 입력되는 경우는 없습니다.

## 입출력 예

|      seoul      |       return        |
| :-------------: | :-----------------: |
| ["Jane", "Kim"] | "김서방은 1에 있다" |

## 답안:

```

function solution(seoul) {
return "김서방은 "+seoul.indexOf("Kim")+"에 있다";
}
```

---

# 6/3

## 문제:

나누어 떨어지는 숫자 배열

## 설명:

array의 각 element 중 divisor로 나누어 떨어지는 값을 오름차순으로 정렬한 배열을 반환하는 함수, solution을 작성해주세요.
divisor로 나누어 떨어지는 element가 하나도 없다면 배열에 -1을 담아 반환하세요.

## 입출력 예

arr divisor return
[5, 9, 7, 10] 5 [5, 10]
[2, 36, 1, 3] 1 [1, 2, 3, 36]
[3,2,6] 10 [-1]

|      arr      | divisor |    return     |
| :-----------: | :-----: | :-----------: |
| [5, 9, 7, 10] |    5    |    [5, 10]    |
| [2, 36, 1, 3] |    1    | [1, 2, 3, 36] |
|    [3,2,6]    |   10    |     [-1]      |

## 답안:

```
function solution(arr, divisor) {
    return arr.filter((v)=> v%divisor === 0).length ===0 ? [-1] : arr.filter((v)=> v%divisor === 0).sort((a, b)=> a-b)

}
```

---

## 문제:

핸드폰 번호 가리기

## 설명:

프로그래머스 모바일은 개인정보 보호를 위해 고지서를 보낼 때 고객들의 전화번호의 일부를 가립니다.
전화번호가 문자열 phone_number로 주어졌을 때, 전화번호의 뒷 4자리를 제외한 나머지 숫자를 전부 \*으로 가린 문자열을 리턴하는 함수, solution을 완성해주세요.

## 입출력 예

| phone_number  |      return      |
| :-----------: | :--------------: |
| "01033334444" | "**\*\*\***4444" |
|  "027778888"  |   "**\***8888"   |

## 답안:

```

function solution(phone_number) {
return phone_number.replace(/\d(?=\d{4})/g, "\*");
}
```

---

## 문제:

음양 더하기

## 설명:

어떤 정수들이 있습니다. 이 정수들의 절댓값을 차례대로 담은 정수 배열 absolutes와 이 정수들의 부호를 차례대로 담은 불리언 배열 signs가 매개변수로 주어집니다. 실제 정수들의 합을 구하여 return 하도록 solution 함수를 완성해주세요.

## 입출력 예

| absolutes |       signs        | return |
| :-------: | :----------------: | :----: |
| [4,7,12]  | [true,false,true]  |   9    |
|  [1,2,3]  | [false,false,true] |   0    |

## 답안:

```
function solution(absolutes, signs) {
    return absolutes.map((v,i)=>signs[i] ?  v :  -v ).reduce((a, c)=> a + c)
}
```

---

6/4

## 문제:

제일 작은 수 제거하기

## 설명:

정수를 저장한 배열, arr 에서 가장 작은 수를 제거한 배열을 리턴하는 함수, solution을 완성해주세요. 단, 리턴하려는 배열이 빈 배열인 경우엔 배열에 -1을 채워 리턴하세요. 예를들어 arr이 [4,3,2,1]인 경우는 [4,3,2]를 리턴 하고, [10]면 [-1]을 리턴 합니다.

## 입출력 예

|    arr    | return  |
| :-------: | :-----: |
| [4,3,2,1] | [4,3,2] |
|   [10]    |  [-1]   |

## 답안:

```

function solution(arr) {
    arr.splice(arr.indexOf(Math.min(...arr)),1);
    arr.length <= 1 ? answer = [-1] : answer = arr
    return answer;
}
```

---

## 문제:

가운데 글자 가져오기

## 설명:

단어 s의 가운데 글자를 반환하는 함수, solution을 만들어 보세요. 단어의 길이가 짝수라면 가운데 두글자를 반환하면 됩니다.

## 입출력 예

|    s    | return |
| :-----: | :----: |
| "abcde" |  "c"   |
| "qwer"  |  "we"  |

## 답안:

```
function solution(s) {
    let answer = '';
    if (s.length % 2 == 0 ) { // 짝수일 경우,
        answer = s[s.length / 2 - 1] + s[s.length / 2];
    } else {
        answer = s[Math.floor(s.length/2)]; // 홀수일 경우, 반내림 하기
    }
    return answer;
}
```

---

## 문제:

수박수박수박수박수박수?

## 설명:

길이가 n이고, "수박수박수박수...."와 같은 패턴을 유지하는 문자열을 리턴하는 함수, solution을 완성하세요. 예를들어 n이 4이면 "수박수박"을 리턴하고 3이라면 "수박수"를 리턴하면 됩니다.

## 입출력 예

|  n  |   return   |
| :-: | :--------: |
|  3  |  "수박수"  |
|  4  | "수박수박" |

## 답안:

```
function solution(n) {
    return "수박".repeat(n).slice(0, n);
}
```

---

# 6/5

## 문제:

없는 숫자 더하기 3

## 설명:

0부터 9까지의 숫자 중 일부가 들어있는 정수 배열 numbers가 매개변수로 주어집니다. numbers에서 찾을 수 없는 0부터 9까지의 숫자를 모두 찾아 더한 수를 return 하도록 solution 함수를 완성해주세요.

## 입출력 예

|      numbers      | result |
| :---------------: | :----: |
| [1,2,3,4,6,7,8,0] |   14   |
|  [5,8,4,0,6,7,9]  |   6    |

## 답안:

```
function solution(numbers) {
    return [0, 1, 2, 3, 4, 5, 6, 7, 8, 9].filter(x => !numbers.includes(x)).reduce((a, b) => a + b);
}

```

---

## 문제:

제일 작은 수 제거하기

## 설명:

정수를 저장한 배열, arr 에서 가장 작은 수를 제거한 배열을 리턴하는 함수, solution을 완성해주세요. 단, 리턴하려는 배열이 빈 배열인 경우엔 배열에 -1을 채워 리턴하세요. 예를들어 arr이 [4,3,2,1]인 경우는 [4,3,2]를 리턴 하고, [10]면 [-1]을 리턴 합니다.

## 입출력 예

|    arr    | return  |
| :-------: | :-----: |
| [4,3,2,1] | [4,3,2] |
|   [10]    |  [-1]   |

## 답안:

```
function solution(arr) {
    arr.splice(arr.indexOf(Math.min(...arr)),1);
    arr.length <= 1 ? answer = [-1] : answer = arr
    return answer;
}
```

---

## 문제:

가운데 글자 가져오기

## 설명:

단어 s의 가운데 글자를 반환하는 함수, solution을 만들어 보세요. 단어의 길이가 짝수라면 가운데 두글자를 반환하면 됩니다.

## 입출력 예

|    s    | return |
| :-----: | :----: |
| "abcde" |  "c"   |
| "qwer"  |  "we"  |

## 답안:

```
function solution(s) {
    let answer = '';
    if (s.length % 2 == 0 ) { // 짝수일 경우,
        answer = s[s.length / 2 - 1] + s[s.length / 2];
    } else {
        answer = s[Math.floor(s.length/2)]; // 홀수일 경우, 반내림 하기
    }
    return answer;
}
```

---

# 6/6

## 문제:

문자열 내림차순으로 배치하기

## 설명:

문자열 s에 나타나는 문자를 큰것부터 작은 순으로 정렬해 새로운 문자열을 리턴하는 함수, solution을 완성해주세요.
s는 영문 대소문자로만 구성되어 있으며, 대문자는 소문자보다 작은 것으로 간주합니다.

## 입출력 예

|     s     |  return   |
| :-------: | :-------: |
| "Zbcdefg" | "gfedcbZ" |

## 답안:

```
function solution(s) {
    return s.split("").sort().reverse().join("");
}
```

---

## 문제:

부족한 금액 계산하기

## 설명:

새로 생긴 놀이기구는 인기가 매우 많아 줄이 끊이질 않습니다. 이 놀이기구의 원래 이용료는 price원 인데, 놀이기구를 N 번 째 이용한다면 원래 이용료의 N배를 받기로 하였습니다. 즉, 처음 이용료가 100이었다면 2번째에는 200, 3번째에는 300으로 요금이 인상됩니다.
놀이기구를 count번 타게 되면 현재 자신이 가지고 있는 금액에서 얼마가 모자라는지를 return 하도록 solution 함수를 완성하세요.
단, 금액이 부족하지 않으면 0을 return 하세요.

## 입출력 예

| price | money | count | result |
| :---: | :---: | :---: | :----: |
|   3   |  20   |   4   |   10   |

## 답안:

```
function solution(price, money, count) {
    let totalPrice = 0;

    for(let i =1; i<=count; i++){
        totalPrice += price * i
    }
    return (money-totalPrice >= 0) ? 0 : Math.abs(money - totalPrice);
}
```

---

## 문제:

문자열 다루기 기본

## 설명:

문자열 s의 길이가 4 혹은 6이고, 숫자로만 구성돼있는지 확인해주는 함수, solution을 완성하세요. 예를 들어 s가 "a234"이면 False를 리턴하고 "1234"라면 True를 리턴하면 됩니다.

## 입출력 예

|    s    | return |
| :-----: | :----: |
| "a1234" | false  |
| "1234"  |  true  |

## 답안:

```

function solution(s) {
    if(s.length === 4 || s.length === 6){
        return s.split("").every(c => !isNaN(c))
    } else {
        return false;
    }
}
```

---

# 6/7

## 문제:

행렬의 덧셈

## 설명:

행렬의 덧셈은 행과 열의 크기가 같은 두 행렬의 같은 행, 같은 열의 값을 서로 더한 결과가 됩니다. 2개의 행렬 arr1과 arr2를 입력받아, 행렬 덧셈의 결과를 반환하는 함수, solution을 완성해주세요.

## 입출력 예

|      arr1       |      arr2       |     return      |
| :-------------: | :-------------: | :-------------: |
| `[[1,2],[2,3]]` | `[[3,4],[5,6]]` | `[[4,6],[7,9]]` |
| `[[4,6],[7,9]]` |   `[[3],[4]]`   |   `[[4],[6]]`   |

## 답안:

```
function solution(arr1, arr2){
    let answer = [] // 배열들을 감싸줄 배열틀
    for(let i = 0; i < arr1.length; i++){
        let temp_arr = []  // 각 배열을 더한 값을 넣어줄 임시 배열
     for(let j  = 0; j < arr1[i].length; j++){
    temp_arr.push(arr1[i][j] + arr2[i][j])
    //temp_arr=arr1[i][j]+arr2[i][j]
  }
        answer.push(temp_arr)  //answer = [temp_arr]
}
    return answer;
}
```

---

## 문제:

직사각형 별찍기

## 설명:

이 문제에는 표준 입력으로 두 개의 정수 n과 m이 주어집니다.
별(\*) 문자를 이용해 가로의 길이가 n, 세로의 길이가 m인 직사각형 형태를 출력해보세요.

## 입력

```
5 3
```

## 출력

```
*****
*****
*****
```

## 답안:

```
process.stdin.setEncoding('utf8');
process.stdin.on('data', data => {
      const n = data.split(" ");
  const a = Number(n[0]),
    b = Number(n[1]);
  // 입력 값 b(3) 만큼 반복문을 돌린다.
  for (let i = 0; i < b; i++) {
    // stars 변수를 초기화 해준다.
    let stars = "";
    // 위 for문이 한번 돌아갈 때 마다 입력 값 a(5) 만큼 반복문을 돌린다.
    for (let j = 0; j < a; j++) {
      // stars = stars + "*"
      stars += "*";
    }
    // 콘솔에 현재 까지 저장된 stars 값을 찍는다. (*****)
    console.log(stars);}
});
```

---

## 문제:

최대공약수와 최소공배수

## 설명:

두 수를 입력받아 두 수의 최대공약수와 최소공배수를 반환하는 함수, solution을 완성해 보세요. 배열의 맨 앞에 최대공약수, 그다음 최소공배수를 넣어 반환하면 됩니다. 예를 들어 두 수 3, 12의 최대공약수는 3, 최소공배수는 12이므로 solution(3, 12)는 [3, 12]를 반환해야 합니다.

## 입출력 예

|  n  |  m  | return  |
| :-: | :-: | :-----: |
|  3  | 12  | [3, 12] |
|  2  |  5  | [1, 10] |

## 답안:

```

function solution(num1, num2) {
    const gcd = (a, b) => a % b === 0 ? b : gcd(b, a % b);
    const lcm = (a, b) => a * b / gcd(a, b);
    return [gcd(num1, num2), lcm(num1, num2)];
}
```

---

# 6/9

## 문제:

같은 숫자는 싫어

## 설명:

배열 arr가 주어집니다. 배열 arr의 각 원소는 숫자 0부터 9까지로 이루어져 있습니다. 이때, 배열 arr에서 연속적으로 나타나는 숫자는 하나만 남기고 전부 제거하려고 합니다. 단, 제거된 후 남은 수들을 반환할 때는 배열 arr의 원소들의 순서를 유지해야 합니다. 예를 들면,arr = [1, 1, 3, 3, 0, 1, 1] 이면 [1, 3, 0, 1] 을 return 합니다.
arr = [4, 4, 4, 3, 3] 이면 [4, 3] 을 return 합니다.
배열 arr에서 연속적으로 나타나는 숫자는 제거하고 남은 수들을 return 하는 solution 함수를 완성해 주세요.

## 입출력 예

|       arr       |  answer   |
| :-------------: | :-------: |
| [1,1,3,3,0,1,1] | [1,3,0,1] |
|   [4,4,4,3,3]   |   [4,3]   |

## 답안:

```
function solution(arr)
{
return arr.filter((val,index) => val != arr[index+1]);
}
```

---

## 문제:

3진법 뒤집기

## 설명:

자연수 n이 매개변수로 주어집니다. n을 3진법 상에서 앞뒤로 뒤집은 후, 이를 다시 10진법으로 표현한 수를 return 하도록 solution 함수를 완성해주세요.

## 입출력 예

| n(10진법) | n(3진법) | 앞뒤 반전(3진법) | 10진법으로 표현 |
| :-------: | :------: | :--------------: | :-------------: |
|    45     |   1200   |       0021       |        7        |

## 답안:

```
function solution(n) {
  const tetra = [];
  while (n > 0) {
    const remainder = n % 3;
    tetra.push(remainder);
    n = Math.floor(n / 3);
  }
  tetra.reverse();
  let sum = 0;
  for (let i = 0; i < tetra.length; i++) {
    sum += tetra[i] * 3 ** i;
  }
  return sum;
}
```

---

## 문제:

예산

## 설명:

S사에서는 각 부서에 필요한 물품을 지원해 주기 위해 부서별로 물품을 구매하는데 필요한 금액을 조사했습니다. 그러나, 전체 예산이 정해져 있기 때문에 모든 부서의 물품을 구매해 줄 수는 없습니다. 그래서 최대한 많은 부서의 물품을 구매해 줄 수 있도록 하려고 합니다.

물품을 구매해 줄 때는 각 부서가 신청한 금액만큼을 모두 지원해 줘야 합니다. 예를 들어 1,000원을 신청한 부서에는 정확히 1,000원을 지원해야 하며, 1,000원보다 적은 금액을 지원해 줄 수는 없습니다.

부서별로 신청한 금액이 들어있는 배열 d와 예산 budget이 매개변수로 주어질 때, 최대 몇 개의 부서에 물품을 지원할 수 있는지 return 하도록 solution 함수를 완성해주세요.

제한사항
d는 부서별로 신청한 금액이 들어있는 배열이며, 길이(전체 부서의 개수)는 1 이상 100 이하입니다.
d의 각 원소는 부서별로 신청한 금액을 나타내며, 부서별 신청 금액은 1 이상 100,000 이하의 자연수입니다.
budget은 예산을 나타내며, 1 이상 10,000,000 이하의 자연수입니다.

## 입출력 예

|      d      | budget | result |
| :---------: | :----: | :----: |
| [1,3,2,5,4] |   9    |   3    |
|  [2,2,3,3]  |   10   |   4    |

## 답안:

```

function solution(d, budget) {
    d.sort((a, b) => a - b);
    while (d.reduce((a, b) => (a + b), 0) > budget) {
      d.pop();
    }

    return d.length;
}

```

---

# 6/10

## 문제:

이상한 문자 만들기

## 설명:

문자열 s는 한 개 이상의 단어로 구성되어 있습니다. 각 단어는 하나 이상의 공백문자로 구분되어 있습니다. 각 단어의 짝수번째 알파벳은 대문자로, 홀수번째 알파벳은 소문자로 바꾼 문자열을 리턴하는 함수, solution을 완성하세요.

## 입출력 예

|         s         |      return       |
| :---------------: | :---------------: |
| "try hello world" | "TrY HeLlO WoRlD" |

## 답안:

```
function solution(s) {
    let answer = '';
    let index = 0;
    for (let spell of s) {
        answer += (index % 2 === 0) ? spell.toUpperCase() : spell.toLowerCase();
        index += 1;
        if (spell === ' ') index = 0;
    }
    return answer;
}
```

---

## 문제:

삼총사

## 설명:

한국중학교에 다니는 학생들은 각자 정수 번호를 갖고 있습니다. 이 학교 학생 3명의 정수 번호를 더했을 때 0이 되면 3명의 학생은 삼총사라고 합니다. 예를 들어, 5명의 학생이 있고, 각각의 정수 번호가 순서대로 -2, 3, 0, 2, -5일 때, 첫 번째, 세 번째, 네 번째 학생의 정수 번호를 더하면 0이므로 세 학생은 삼총사입니다. 또한, 두 번째, 네 번째, 다섯 번째 학생의 정수 번호를 더해도 0이므로 세 학생도 삼총사입니다. 따라서 이 경우 한국중학교에서는 두 가지 방법으로 삼총사를 만들 수 있습니다.

한국중학교 학생들의 번호를 나타내는 정수 배열 number가 매개변수로 주어질 때, 학생들 중 삼총사를 만들 수 있는 방법의 수를 return 하도록 solution 함수를 완성하세요.

## 입출력 예

|          number          | result |
| :----------------------: | :----: |
|    [-2, 3, 0, 2, -5]     |   2    |
| [-3, -2, -1, 0, 1, 2, 3] |   5    |
|      [-1, 1, -1, 1]      |   0    |

## 답안:

```
function solution(number) {
    let sum = 0;
    for(let i = 0; i < number.length; i++){
        for(let j = i+1; j < number.length; j++){
            for(let k = j+1; k < number.length; k++)
                if(number[i]+number[j]+number[k] === 0)
                    sum += 1;
        }
    }
    return sum;
}
```

---

## 문제:

시저 암호

## 설명:

어떤 문장의 각 알파벳을 일정한 거리만큼 밀어서 다른 알파벳으로 바꾸는 암호화 방식을 시저 암호라고 합니다. 예를 들어 "AB"는 1만큼 밀면 "BC"가 되고, 3만큼 밀면 "DE"가 됩니다. "z"는 1만큼 밀면 "a"가 됩니다. 문자열 s와 거리 n을 입력받아 s를 n만큼 민 암호문을 만드는 함수, solution을 완성해 보세요.

## 입출력 예

|    s    |  n  | result  |
| :-----: | :-: | :-----: |
|  "AB"   |  1  |  "BC"   |
|   "z"   |  1  |   "a"   |
| "a B z" |  4  | "e F d" |

## 답안:

```

function solution(s, n) {
    return s.split('').map(char => {
        if (char === ' ') return char;
        let base = char.toUpperCase() === char ? 'A'.charCodeAt(0) : 'a'.charCodeAt(0);
        return String.fromCharCode(((char.charCodeAt(0) - base + n) % 26) + base);
    }).join('');
}

```
