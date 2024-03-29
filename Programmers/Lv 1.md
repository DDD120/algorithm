
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
[가장 가까운 같은 글자](https://school.programmers.co.kr/learn/courses/30/lessons/142086) (연습문제)
```javascript
function solution(s) {
    const answer = [...s].map((char, index) => {
        if(index === 0) return -1;
        const searchIndex = s.lastIndexOf(char, index - 1);
        return searchIndex < 0 ? -1 : index - searchIndex;
    })
    return answer;
}
```
[소수 찾기](https://school.programmers.co.kr/learn/courses/30/lessons/12921) (연습문제)
```javascript
function solution(n) {   
    const arr = Array(n + 1).fill(true).fill(false, 0, 2);
    for(let i = 2;i <= Math.sqrt(n);i++){
        if(arr[i]){
            for(let j = i * i;j <= n;j += i){
                arr[j] = false;
            }
        }
    }
    
    const answer = arr.filter((value) => value).length;
    return answer;
}
```
[과일 장수](https://school.programmers.co.kr/learn/courses/30/lessons/135808) (연습문제)
```javascript
function solution(k, m, score) {
    let answer = 0;
    const sortScore = score.sort((a,b) => b - a);
    const limitBox = Math.floor(score.length / m);
    
    for(let i = 0;i < limitBox;i++){
        answer += sortScore.slice(m * i, m + m * i)[m-1] * m;
    }
    
    return answer;
}
```
[명예의 전당(1)](https://school.programmers.co.kr/learn/courses/30/lessons/138477) (연습 문제)
```javascript
function solution(k, score) {
    const hof = [];
    const answer = score.map((s, i) => {
        const lowest = hof.at(-1);
        if(i >= k && lowest >= s) return lowest;
        if(i >= k && lowest < s) hof.pop();
        hof.push(s);
        hof.sort((a,b) => b - a);
        return hof.at(-1);
    })
    
    return answer;
}
```
[기사단원의 무기](https://school.programmers.co.kr/learn/courses/30/lessons/136798) (연습 문제)
```javascript
function solution(number, limit, power) {
    const divisor = []
    for(let num = 1; num <= number; num++){
        let count = 1
        for(let i = 1; i <= num / 2; i++){
	        if(!(num % i)) count += 1
	    }
        divisor.push(count)
    }
      
    const answer = divisor.reduce((acc, cur) => {
        return cur > limit ? acc += power : acc += cur
    }, 0)
    return answer
}
```
[추억 점수](https://school.programmers.co.kr/learn/courses/30/lessons/176963) (연습 문제)
```javascript
function solution(name, yearning, photo) {
    const answer = photo.map((array) => (
        array.reduce((acc, cur) => (
            acc += yearning[name.indexOf(cur)] ?? 0
        ), 0))
    )
    return answer
}
```
[카드 뭉치](https://school.programmers.co.kr/learn/courses/30/lessons/159994) (연습 문제)
```javascript
function solution(cards1, cards2, goal) {
    let index1 = 0
    let index2 = 0

    const fail = goal.some((word) => {
        if(word !== cards1[index1] && word !== cards2[index2]) return true
        if(word === cards1[index1]) index1 += 1
        if(word === cards2[index2]) index2 += 1
        return false
    })
    
    return fail ? "No" : "Yes"
}
```
[덧칠하기](https://school.programmers.co.kr/learn/courses/30/lessons/161989) (연습문제)
```javascript
function solution(n, m, section) {
    let answer = 0
    let next = 0
    
    section.forEach((index) => {
        if(next > index) return
        answer += 1
        next = index + m
    })
    
    return answer
}
```
[숫자 짝궁](https://school.programmers.co.kr/learn/courses/30/lessons/131128) (연습문제)
```javascript
function solution(X, Y) {
    let mate = ''
    const x = [...X]
    const y = [...Y]
    
    for(let i = 0;i < 10;i++){
        const a = x.filter((char) => Number(char) === i).length
        const b = y.filter((char) => Number(char) === i).length
        mate += String(i).repeat(Math.min(a,b))
    }
    
    if(!mate) return "-1"
    if(Number(mate) === 0) return "0"
    const answer = [...mate].sort((a,b) => Number(b) - Number(a)).join("")
    
    return answer
    
}
```
[옹알이(2)](https://school.programmers.co.kr/learn/courses/30/lessons/133499) (연습문제)
```javascript
function solution(babbling) {
    let answer = 0
    const ableBabbling = ["aya", "ye", "woo", "ma"]
    babbling.forEach((bab) => {
        ableBabbling.forEach((able) => {
            if(bab.includes(`${able}${able}`)) return
            bab = bab.replaceAll(able, " ")
        })
        if(!bab.trim()) answer++
    })
    
    return answer
}
```
[문자열 나누기](https://school.programmers.co.kr/learn/courses/30/lessons/140108) (연습문제)
```javascript
function solution(s) {
    let answer = 0
    let xChar = null
    let xCount = 1
    let yCount = 0

    s.split('').forEach((cur, index, array) => {
        if(index === array.length - 1) return answer++
        if(!xChar) return xChar = cur
        cur === xChar ? xCount++ : yCount++
        if(xCount === yCount) {
            answer++
            xChar = null
            xCount = 1
            yCount = 0
        }
        
    })
    
    return answer
}
```
[둘만의 암호](https://school.programmers.co.kr/learn/courses/30/lessons/155652) (연습문제)
```javascript
function solution(s, skip, index) {
    let answer = ''
    const skipRe = new RegExp(`[^${skip}]`, 'g')
    const alphabet = 'abcdefghijklmnopqrstuvwxyz'.match(skipRe)

    for(const c of s){
        const i = alphabet.indexOf(c) + index
        answer += alphabet[i % alphabet.length]
    }

    return answer
}
```
[대충 만든 자판](https://school.programmers.co.kr/learn/courses/30/lessons/160586) (연습문제)
```javascript
function solution(keymap, targets) {
    const answer = targets.map((target) => {
        const a = target.split('').reduce((acc, cur) => {
            let minIndex
            keymap.forEach((key) => {
                const index = key.indexOf(cur) + 1
                if(!index) return
                if(index < minIndex || !minIndex) minIndex = index
            })
            return minIndex ? acc += minIndex : undefined
        }, 0) 
        return a ? a : -1
    })
    
    return answer
}
```
[햄버거 만들기](https://school.programmers.co.kr/learn/courses/30/lessons/133502) (연습문제)
```javascript
function solution(ingredient) {
    let answer = 0
    const counter = []

    for(const i of ingredient){
        counter.push(i)
        if(counter.length >= 4){
            if(counter[counter.length - 4] === 1 &&
               counter[counter.length - 3] === 2 &&
               counter[counter.length - 2] === 3 &&
               counter[counter.length - 1] === 1){
                    answer += 1
                    counter.pop()
                    counter.pop()
                    counter.pop()
                    counter.pop()
               }
        }
    }
    
    return answer
}
```
[달리기 경주](https://school.programmers.co.kr/learn/courses/30/lessons/178871) (연습문제)
```javascript
function solution(players, callings) {
    const playersMap = players.reduce((map, player, index) => {
        map.set(player, index)
        return map
    }, new Map)

    callings.forEach((calling) => {
        const i = playersMap.get(calling)
        playersMap.set(players[i], i - 1)
        playersMap.set(players[i - 1], i)
        players.splice(i - 1, 2, players[i], players[i - 1])
    })
    return players
}
```
[바탕화면 정리](https://school.programmers.co.kr/learn/courses/30/lessons/161990) (연습문제)
```javascript
function solution(wallpaper) {
    const lu = wallpaper.map((row) => row.indexOf("#"))
    const rd = wallpaper.map((row) => row.lastIndexOf("#"))

    const lux = lu.findIndex((num) => num > -1)
    const luy = Math.min(...lu.filter((p) => p !== -1))
    const rdx = rd.length - rd.reverse().findIndex((num) => num > -1)
    const rdy = Math.max(...rd) + 1
    
    return [lux, luy, rdx, rdy]
}
```
[공원 산책](https://school.programmers.co.kr/learn/courses/30/lessons/172928) (연습문제)
```javascript
function solution(park, routes) {
    const current = []
    park.some((row, index) => {
        const sIndex = row.indexOf("S")
        if(sIndex !== -1){
            current.push(index, sIndex)
            return true
        }
    })

    routes.forEach((route) => {        
        const op = route[0]
        const step = Number(route[2])
        let isBlock = false

        const move = (dir, isPlus) => {
            const arrive = current[dir] + (isPlus ? step : -step)
            if(arrive < 0 || (dir === 0 ?
               arrive >= park.length : arrive >= park[0].length)) return
            for(let i = 1;i <= step; i++){
                const g = current[dir] + (isPlus ? i : -i)
                const going = dir === 0 ? 
                      park[g][current[1]] : park[current[0]][g] 
                if(going === "X") {
                    isBlock = true
                    break
                } 
            }
            if(!isBlock) current[dir] = arrive
        }

        switch(op){
            case "N":
                move(0,false)
                break
            case "E":
                move(1,true)
                break
            case "S":
                move(0, true)
                break
            case "W":
               move(1, false)
                break
        }
    })

    return current
}
```
[부족한 금액 계산하기](https://school.programmers.co.kr/learn/courses/30/lessons/82612) (위클리 챌린지)
```javascript
function solution(price, money, count) {
    let pay = 0

    for(let i=1;i <= count;i++){
        pay += price * i
    }
    
    const answer = pay - money
    
    return answer >= 0 ? answer : 0
}
```
[3진법 뒤집기](https://school.programmers.co.kr/learn/courses/30/lessons/68935) (월간 코드 챌린지 시즌1)
```javascript
function solution(n) {
    return parseInt(n.toString(3).split('').reverse().join(''), 3)
}
```
[예산](https://school.programmers.co.kr/learn/courses/30/lessons/12982) (Summer/Winter Coding(~2018))
```javascript
function solution(d, budget) {
    let answer
    d.sort((a,b) => a-b)
    for(let i=d.length;i >= 0;i--){
        const array = d.slice(0, i)
        const sum = array.reduce((acc, cur) => acc += cur, 0)
        if(sum <= budget){
            answer = i
            break
        }
    }
    return answer
}
```
[최소직사각형](https://school.programmers.co.kr/learn/courses/30/lessons/86491) (완전탐색)
```javascript
function solution(sizes) {
    const sortSizes = sizes.map((size) => size.sort((a,b) => a-b))
    const w = Math.max(...sortSizes.map((size) => size[0]))
    const h = Math.max(...sortSizes.map((size) => size[1]))
    
    return w * h
}
```
[[1차] 비밀지도](https://school.programmers.co.kr/learn/courses/30/lessons/17681) (2018 KAKAO BLIND RECRUITMENT)
```javascript
function solution(n, arr1, arr2) {
    const map = arr1.map((row, index) => {
        const a1 = row.toString(2).padStart(n, "0")
        const a2 = arr2[index].toString(2).padStart(n, "0")
        
        const decode = a1.split('').map((chr, index) => 
            Number(chr) + Number(a2[index]) ? "#" : " " 
        ).join("")
        
        return decode
    })
    
    return  map
}
```
[숫자 문자열과 영단어](https://school.programmers.co.kr/learn/courses/30/lessons/81301) (2021 카카오 채용연계형 인턴십)
```javascript
function solution(s) {
    let string = s
    const num = {
        zero: 0,
        one: 1,
        two: 2,
        three: 3,
        four: 4,
        five: 5,
        six: 6,
        seven: 7,
        eight: 8,
        nine: 9
    }

    const keys = Object.keys(num).join('|')
    const words = string.match(new RegExp(`${[keys]}`,'g'))

    words?.forEach((word) => {
        string = string.replace(word, num[word])
    })

    return Number(string)
}
```
[k번째수](https://school.programmers.co.kr/learn/courses/30/lessons/42748) (정렬)
```javascript
function solution(array, commands) {
    const answer = commands.map((command) => {
        const [i,j,k] = command
        return array.slice(i-1, j).sort((a,b) => a-b)[k-1]
    })

    return answer
}
```
[두 개 뽑아서 더하기](https://school.programmers.co.kr/learn/courses/30/lessons/68644) (월간 코드 챌린지 시즌1)
```javascript
function solution(numbers) {
    const results = []
    numbers.forEach((fixed, index, origin) => {
        const rest = origin.slice(index + 1)
        const sum = rest.map((num) => fixed + num)
        results.push(...sum)
    });

    const answer = [...new Set(results)].sort((a,b) => a-b)
    return answer
}
```
[모의고사](https://school.programmers.co.kr/learn/courses/30/lessons/42840) (완전탐색)
```javascript
function solution(answers) {
    const answer = []
    const scores = [0,0,0]
    answers.forEach((answer, index) => {
        if(answer === Number("12345"[index % 5])) scores[0]++
        if(answer === Number("21232425"[index % 8])) scores[1]++
        if(answer === Number("3311224455"[index % 10])) scores[2]++
    })

    scores.forEach((score, index) => {
        if(score === Math.max(...scores)) answer.push(index+1)
    })

    return answer
}
```
[소수 만들기](https://school.programmers.co.kr/learn/courses/30/lessons/12977) (Summer/Winter Coding(~2018))
```javascript
function solution(nums) {
    let answer = 0
    const sums = []
    for(let i=0;i < nums.length-2;i++){
        for(let j=i+1;j < nums.length-1;j++){
            for(let k=j+1;k < nums.length;k++){
                sums.push(nums[i] + nums[j] + nums[k])
            }
        }
    }

    sums.forEach((sum) => {
        let isPrime = true
        for(let i=2;i <= sum/2;i++){
            if(sum % i === 0){
                isPrime = false
                break
            }
        }
        if(isPrime) answer += 1
    })

    return answer
}
```
[실패율](https://school.programmers.co.kr/learn/courses/30/lessons/42889) (2019 KAKAO BLIND RECRUITMENT)
```javascript
function solution(N, stages) {
    const players = []
    let reach = stages.length
    for(let i=1;i <= N;i++){
        players[i-1] = [i, 0]
        stages.forEach((stage) => {
            if(stage === i) players[i-1] = [i, players[i-1][1] + 1]
        })
    }
    const answer = players.map((player) => {
        const fail = [player[0], player[1] / reach]
        reach -= player[1]
        return fail
    }).sort((a,b) => b[1]-a[1]).map((stage) => stage[0])

    return answer
}
```
[[1차] 다트 게임](https://school.programmers.co.kr/learn/courses/30/lessons/17682) (2018 KAKAO BLIND RECRUITMENT)
```javascript
function solution(dartResult) {
    const score = []
     const scorecard = {
        S: 1,
        D: 2,
        T: 3,
        "*": 2,
        "#": -1
    }
    const set = dartResult.matchAll(/\d+[SDT][*#]?/g)
    Array.from(set, res => res[0]).forEach((s, i) => {
        const option = scorecard[s.match(/[*#]/)] ?? 1
        score[i] = s.match(/\d+/) ** scorecard[s.match(/[SDT]/)] * option
        if(option === 2) score[i-1] *= option
    })
    return score[0] + score[1] + score[2]
}
```
[로또의 최고 순위와 최저 순위](https://school.programmers.co.kr/learn/courses/30/lessons/77484) (2021 Dev-Matching: 웹 백엔드 개발자(상반기))
```javascript
function solution(lottos, win_nums) {
    const exclude = lottos.filter((lotto) => !win_nums.includes(lotto))
    const zero = exclude.filter((num) => num === 0).length
    const rank = exclude.length + 1
    const highest =  rank - zero === 7 ? 6 : rank - zero
    const lowest = rank === 7 ? 6 : rank

    return [highest,lowest]
}
```
[체육법](https://school.programmers.co.kr/learn/courses/30/lessons/42862) (탐욕법(Greedy))
```javascript
function solution(n, lost, reserve) {
    const realLost = lost.filter((num) => {
        const i = reserve.indexOf(num)
        if(i > -1){
            reserve.splice(i,1)
            return false
        }
        return true
    })

    const lostCount = realLost.sort().filter((num) => {
        return !reserve.sort().some((re, i) => {
            if([re - 1, re + 1].includes(num)){
                reserve.splice(i, 1)
                return true
            }
        })
    }).length

    return n - lostCount
}
```
[완주하지 못한 선수](https://school.programmers.co.kr/learn/courses/30/lessons/42576) (해시)
```javascript
function solution(participant, completion) {
    let answer

    const objCompletion = completion.reduce((obj, cur) => {
        obj[cur] = obj[cur] ? obj[cur] += 1 : 1
        return obj
    }, {})

    participant.some((p) => {
        if(!objCompletion[p]) return answer = p
        objCompletion[p] -= 1
    })

    return answer
}
```
[크레인 인형뽑기 게임](https://school.programmers.co.kr/learn/courses/30/lessons/64061) (2019 카카오 개발자 겨울 인턴십)
```javascript
function solution(board, moves) {
    let answer = 0
    const stack = []
    moves.forEach((move) => {
        const index = move - 1
        board.some((row) => {
            if(row[index]){
                if(stack.at(-1) === row[index]){
                    stack.pop()
                    answer += 2
                } else {
                    stack.push(row[index])
                }
                row[index] = 0
                return true
            }
        })
    })

    return answer
}
```
[신규 아이디 추천](https://school.programmers.co.kr/learn/courses/30/lessons/72410) (2021 KAKAO BLIND RECRUITMENT)
```javascript
function solution(new_id) {
    new_id = new_id.toLowerCase()
                        .replace(/[^a-z\d\-\_\.]/g,'')
                        .replace(/[.]{2,}/g,'.')
                        .replace(/^[.]|[.]$/g,'')

    const idLength = new_id.length
    if(!idLength) new_id = 'a'
    if(idLength >= 16) new_id = new_id.slice(0, 15).replace(/^[.]|[.]$/g,'')
    if(idLength <= 2) new_id = new_id.padEnd(3, new_id.at(-1))


    return new_id
}
```
[개인정보 수집 유효기간](https://school.programmers.co.kr/learn/courses/30/lessons/150370) (2023 KAKAO BLIND RECRUITMENT)
```javascript
function solution(today, terms, privacies) {
    const answer = []

    terms.forEach((term) => {
        privacies.forEach((privacie, i) => {
            if(term[0] !== privacie.at(-1)) return
            const date = new Date(privacie.slice(0,10))
            const addMonth = date.getMonth() + Number(term.split(' ')[1])
            const setDate = new Date(date.setMonth(addMonth))
            if(new Date(today) >= setDate) answer.push(i+1)
        })
    })

    return answer.sort((a,b) => a-b)
}
```
[신고 결과 받기](https://school.programmers.co.kr/learn/courses/30/lessons/92334) (2022 KAKAO BLIND RECRUITMENT)
```javascript
function solution(id_list, report, k) {
    const count = id_list.reduce((obj, id) => {
        obj[id] = new Set()
        return obj
    }, {})

    report.forEach((re) => {
        const [user, reportedUser] = re.split(' ')
        count[reportedUser].add(user)
    })

    const answer = id_list.map((id) => {
        let mail = 0
        for(let c in count){
            if(count[c].size >= k && count[c].has(id)) mail += 1
        }
        return mail
    })

    return answer
}
```
