
### 프로그래머스 Lv 1 문제 내가 등록한 답변 모음

[짝수와 홀수](https://school.programmers.co.kr/learn/courses/30/lessons/12937) (연습문제)

  ```javascript
    function solution(num) {
	    const answer = num % 2 === 0 ? "Even" : "Odd";
	    return answer;
    }
 ```


[약수의 합](https://school.programmers.co.kr/learn/courses/30/lessons/12928) (연습문제)

```javascript
 function solution(n) {
	    const array = [n];

	    for(let i = 1; i <= n /2; i++){
	        if(n % i === 0){
	            array.push(i);
	        }
	    }

	    const answer = array.reduce((acc, cur) => acc + cur, 0);

	    return answer;
 }
```
[평균 구하기](https://school.programmers.co.kr/learn/courses/30/lessons/12944) (연습문제)

```javascript
function solution(arr) {
    const answer = arr.reduce((acc, val) => acc += val) / arr.length
    return answer;
}
```

   [자릿수 더하기](https://school.programmers.co.kr/learn/courses/30/lessons/12931) (연습문제)

```javascript
function solution(n){
  const answer = String(n).split('').map(v => Number(v)).reduce((a,b) => a + b)

  return answer;
}
```

[자연수 뒤집어 배열로 만들기](https://school.programmers.co.kr/learn/courses/30/lessons/12932) (연습문제)

```javascript
function solution(n) {
    const arr = String(n).split('').reverse().map(v => Number(v));
    
    return arr;
}
```

[문자열 내 p와 y의 개수](https://school.programmers.co.kr/learn/courses/30/lessons/12916) (연습문제)

```javascript
function solution(s){
    let p = 0;
    let y = 0;
    
    const array = Array.from(s.toUpperCase());
    
    array.forEach((val) => {
        if(val === 'P') return p += 1;
        if(val === 'Y') return y += 1;
     })
    
    return  p === y ? true : false;
}
```

[정수 제곱근 판별](https://school.programmers.co.kr/learn/courses/30/lessons/12934) (연습문제)
```javascript
function solution(n) {
    const sqrt = Math.sqrt(n)
    const answer =  sqrt === parseInt(sqrt)  ? Math.pow((sqrt + 1), 2) : -1;
    return answer;
}
```
[나머지가 1이 되는 수 찾기](https://school.programmers.co.kr/learn/courses/30/lessons/87389) (월간 코드 챌린지 시즌3)
```javascript
function solution(n) {
    for(let answer = 0; answer < n; answer++){    
        if (n % answer === 1) return answer
    }
    return answer;
}
```
[정수 내림차순으로 배치하기](https://school.programmers.co.kr/learn/courses/30/lessons/12933) (연습문제)

```javascript
function solution(n) {
    const answer = String(n).split('').map(v => Number(v)).sort((a,b) => b-a).join('')
    return parseInt(answer);
}
```
[문자열을 정수로 바꾸기](https://school.programmers.co.kr/learn/courses/30/lessons/12925) (연습문제)

```javascript
function solution(s) {
    const answer = parseInt(s);
    return answer;
}
```
[하샤드 수](https://school.programmers.co.kr/learn/courses/30/lessons/12947) (연습문제)
```javascript
function solution(x) {
    return x % String(x).split('').reduce((acc, val) => acc += +val , 0) === 0 
}
```
[두 정수 사이의 합](https://school.programmers.co.kr/learn/courses/30/lessons/12912) (연습문제)
```javascript
function solution(a, b) {
    let answer = 0;
    let n = a;
    let m = b;
    
    if(a > b){
        n = b;
        m = a;
    }
    
    for(let i = n; i <= m; i++){
        answer += i
    }
    
    return answer
}
```
[콜라츠 추측](https://school.programmers.co.kr/learn/courses/30/lessons/12943) (연습문제)
```javascript
function solution(num) {
    let answer = 0;
    
    do {
       num === 1 ? break : answer === 500 ? answer = -1 :num % 2 === 0 ? num /= 2 : num * 3 + 1
        
        
        
        answer++
    } while(num !== 1)
    
    return answer;
}
```
[서울에서 김서방 찾기](https://school.programmers.co.kr/learn/courses/30/lessons/12919) (연습문제)
```javascript
function solution(seoul) {    
    return `김서방은 ${seoul.indexOf('Kim')}에 있다`
}
```
[나누어 떨어지는 숫자 배열](https://school.programmers.co.kr/learn/courses/30/lessons/12910) (연습문제)
```javascript
function solution(arr, divisor) {
    const answer = arr.filter((element) => !(element % divisor));
    answer.sort((a, b) =>  a - b);
    if(!answer.length) answer.push(-1);
    return answer;
}
```

[핸드폰 번호 가리기](https://school.programmers.co.kr/learn/courses/30/lessons/12948) (연습문제)

```javascript
function solution(phone_number) {
    let answer = '';
    const phoneNumLength = phone_number.length
    if(phoneNumLength < 4 || phoneNumLength >20) return;
    const star = "*".repeat(phone_number.substring(0,phoneNumLength - 4).length);
    const num =  phone_number.substring(phoneNumLength - 4,phoneNumLength);
    answer = star.concat(num);
    return answer;
}
```
[음양 더하기](https://school.programmers.co.kr/learn/courses/30/lessons/76501) (월간 코드 챌린지 시즌2)
```javascript
function solution(absolutes, signs) {
    const answer = absolutes.reduce((arr, crv, idx) => 
         arr + (signs[idx] ? crv : crv * -1), 0)
  
    return answer;
} 
```
[제일 작은 수 제거하기](https://school.programmers.co.kr/learn/courses/30/lessons/12935) (연습문제)
```javascript
function solution(arr) {
    var answer = [];
    if(arr.length === 1){
        answer.push(-1);
    }else{
        min = Math.min(...arr);
        answer = arr.filter(n => n !== min)
    }
    return answer;
} 
```
[없는 숫자 더하기](https://school.programmers.co.kr/learn/courses/30/lessons/86051) (월간 코드 챌린지 시즌3)
```javascript
function solution(numbers) {
    const array = Array.from(Array(10).keys());
    
    const result = array.filter((arr) => {
        return !numbers.includes(arr)
    })
    
    const answer = result.reduce((arr, cur) => arr + cur ,0);
    return answer;
}
```
[가운데 글자 가져오기](https://school.programmers.co.kr/learn/courses/30/lessons/12903) (연습문제)

```javascript
function solution(s) {
    return s.length % 2 === 0 ? s.substr(s.length/2-1,2) : s.substr(s.length/2,1)
}
```

[박수박수박수박수박수?](https://school.programmers.co.kr/learn/courses/30/lessons/12922) (연습문제)
```javascript
function solution(n) {
    let answer = "";
    let i = 1;
    while(i <= n){
        if(i % 2) answer = answer.concat("수");
        else answer = answer.concat("박");
        i++
    }
    return answer;
}
```

[내적](https://school.programmers.co.kr/learn/courses/30/lessons/70128) (월간 코드 챌린지 시즌1)
```javascript
function solution(a, b) {
   const answer = a.reduce((acc, cur, index) => {
         return acc += cur * b[index]
    }, 0);
    
    return answer;
}
```

[문자열 내림차순으로 배치하기](https://school.programmers.co.kr/learn/courses/30/lessons/12917) (연습문제)
```javascript
function solution(s) {
    const sortArray = (arr) => arr.sort((a,b) => a > b ? -1 : 1);
    const upper = s.match(/[A-Z]/g) ?? [];
    const lower = Array.from(s).filter(n => !upper.includes(n));
    const answer = [...sortArray(lower), ...sortArray(upper)].join('');

    return answer;
}
```

[약수의 개수와 덧셈](https://school.programmers.co.kr/learn/courses/30/lessons/77884) (월간 코드 챌린지 시즌2)
```javascript
function solution(left, right) {
    let answer = 0;
    const 약수의수 = (num) => {
        let count = 1;
        for(let i = 1; i <= num / 2; i++){
            if(num % i === 0) count += 1;
        }
        return count;
    }
    for(let i = left; i <= right; i++){
        const count = 약수의수(i);
        count % 2 === 0 ? answer += i : answer -= i
    }
    
    return answer;
}
```
[문자열 다루기 기본](https://school.programmers.co.kr/learn/courses/30/lessons/12918) (연습문제)
```javascript
function solution(s) {
    return /^\d{4}$|^\d{6}$/.test(s);
}
```
[행렬의 덧셈](https://school.programmers.co.kr/learn/courses/30/lessons/12950)
```javascript
function solution(arr1, arr2) {
    return arr1.map((arr, index) => arr.map((a, i) => a + arr2[index][i]));
}
```
[직사각형 별찍기](https://school.programmers.co.kr/learn/courses/30/lessons/12969) (연습문제)
```javascript
process.stdin.setEncoding('utf8');
process.stdin.on('data', data => {
    const n = data.split(" ");
    const a = Number(n[0]), b = Number(n[1]);
    let star = "";
    for(let i = 0; i < b; i++){
        for(let j = 0; j < a; j++){
            star += "*"
        }
        star += "\n"
    }
});
```

[최대공약수와 최소공배수](https://school.programmers.co.kr/learn/courses/30/lessons/12940) (연습문제)
```javascript
function solution(n, m) {
    let a = n;
    let b = m;
    let r;
    
    while(a % b !== 0){
        r = a % b;
        a = b;
        b = r;
    }
    
    const 최대공약수 = b;
    const 최소공배수 = n * m / 최대공약수;
    
    return [최대공약수,최소공배수];
}
```
[같은 숫자는 싫어](https://school.programmers.co.kr/learn/courses/30/lessons/12906) (스택/큐)
```javascript
function solution(arr){
    const answer = [];
    arr.forEach((value) => {
        if(answer.at(-1) === value) return
        answer.push(value);
    })
    
    return answer;
}
```
[이상한 문자 만들기](https://school.programmers.co.kr/learn/courses/30/lessons/12930) (연습문제)
```javascript
function solution(s) {
   const answer = s.split(' ').map((word) => word.split('').map((v, i) => i % 2 === 0 ? v.toUpperCase() : v.toLowerCase()).join('')).join(' ')
        
    return answer;
}
```

[시저 암호](https://school.programmers.co.kr/learn/courses/30/lessons/12926) (연습문제)
```javascript
function solution(s, n) {
    const alphabet = Array.from({ length: 26 }, (v, i) => String.fromCharCode(i + 65));
    
    const answer = [...s].map((char) => {
        if(char === " ") return " ";
        const isUpperCase = char === char.toUpperCase();
        const cipher = alphabet[(alphabet.indexOf(char.toUpperCase()) + n) % 26]
        return isUpperCase ? cipher : cipher.toLowerCase();
    }).join("");
    
    return answer;
}
```
[삼총사](https://school.programmers.co.kr/learn/courses/30/lessons/131705) (연습문제)
```javascript
function solution(number) {
    const getTrio = (arr, select) => {
        if (select === 1) return arr.map((el) => [el])
        const result = []
        
        arr.forEach((fixed, index) => {
            const comb = getTrio(arr.slice(index + 1), select - 1)
            const att = comb.map((el) => [fixed, ...el])
            result.push(...att)
        })
        
        return result
    }
    
    const answer = getTrio(number, 3).filter((trio) => 
        trio.reduce((acc, cur) => acc += cur, 0) === 0
    ).length
    
    return answer
}
```
[문자열 내 마음대로 정렬하기](https://school.programmers.co.kr/learn/courses/30/lessons/12915) (연습문제)
```javascript
function solution(strings, n) {
    return strings.sort((a,b) => {
        if(a[n] < b[n]) return -1;
        if(a[n] === b[n]) return a < b ? -1 : 1;
        if(a[n] > b[n]) return 1;
    })
}
```
[크기가 작은 부분 문자열](https://school.programmers.co.kr/learn/courses/30/lessons/147355) (연습문제)
```javascript
function solution(t, p) {
    const answer = [...t].filter((num, idx) => {
        if(idx >= t.length - p.length + 1) return
        return +t.substr(idx, p.length) <= +p;
    }).length;
    return answer;
}
```
[콜라 제](https://school.programmers.co.kr/learn/courses/30/lessons/132267) (연습문제)
```javascript
function solution(a, b, n) {
    let receivedBottle = 0;
    
    const getBottle = (a, b, n) => {
        if(a > n) return;
        const currentbottle = n - (Math.floor(n/a) * a) + Math.floor(n/a) * b;
        receivedBottle += Math.floor(n/a) * b;
        getBottle(a, b, currentbottle);
    }
    getBottle(a, b, n);
    return receivedBottle;
}
```
[푸드 파이트 대회](https://school.programmers.co.kr/learn/courses/30/lessons/134240)  (연습문제)
```javascript
function solution(food) {
    const arr = food.map((num, index) => {
        return Array(Math.floor(num/2)).fill(index);
    }).flat();
        
    return `${arr.join("")}0${arr.reverse().join("")}`;
}
```
[2016년](https://school.programmers.co.kr/learn/courses/30/lessons/12901) (연습문제)
```javascript
function solution(a, b) {
    const week = ["SUN","MON","TUE","WED","THU","FRI","SAT"];
    return week[new Date(2016,a-1,b).getDay()];
}
```
[폰켓몬](https://school.programmers.co.kr/learn/courses/30/lessons/1845) (해시)
```javascript
function solution(nums) {
    const bring = nums.length / 2;
    const uniqueNums = [...new Set(nums)];
    return uniqueNums.length > bring ? bring : uniqueNums.length
}
```
[키패드 누르기](https://school.programmers.co.kr/learn/courses/30/lessons/67256) (2020 카카오 인턴십)
```javascript
function solution(numbers, hand) {
    let left = "*", right = "#";
    
    const position = {
        1: [0,0], 2: [0,1], 3: [0,2],
        4: [1,0], 5: [1,1], 6: [1,2],
        7: [2,0], 8: [2,1], 9: [2,2],
        "*": [3,0], 0: [3,1], "#": [3,2],
    }
    
    const calculation = (nowPos, number) => {
        return Math.abs(position[nowPos][0] - position[number][0]) + Math.abs(position[nowPos][1] - position[number][1])
    }
    
    
    const arr = numbers.map((num) => {
        if(num % 3 === 1) {
            left = num;
            return "L";
        }
        
        if(num !== 0 && num % 3 === 0) {
            right = num;
            return "R";
        }
        if(calculation(left,num) < calculation(right,num)){
           left = num;
            return "L";
        }
        if(calculation(left,num) > calculation(right,num) ){
           right = num;
            return "R";
        }
        if(calculation(left, num) === calculation(right, num)){
                if(hand === "left"){
                    left = num;
                    return "L"
                } else {
                    right = num;
                    return "R"
                }

          }
    })
    
   const answer = arr.join("");
    
    return answer;
}
```

> Written with [StackEdit](https://stackedit.io/).