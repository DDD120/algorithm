### 프로그래머스 Lv 2 문제 내가 등록한 답변 모음

[최댓값과 최솟값](https://school.programmers.co.kr/learn/courses/30/lessons/12939) (연습문제)
  ```javascript
  function solution(s) {
      const nums = s.split(' ')
      return `${Math.min(...nums)} ${Math.max(...nums)}`
  }
 ```
[JadenCase 문자열 만들기](https://school.programmers.co.kr/learn/courses/30/lessons/12951) (연습문제)
  ```javascript
function solution(s) {
    return s.toLowerCase().split(" ").map((word) => 
            word.charAt(0).toUpperCase() + word.slice(1)
        ).join(" ")
}
 ```
[최솟값 만들기](https://school.programmers.co.kr/learn/courses/30/lessons/12941) (연습문제)
  ```javascript
function solution(A,B){
    A.sort((a,b) => a-b)
    B.sort((a,b) => b-a)

    const answer = A.reduce((acc, cur, i) => {
        acc += cur * B[i]
        return acc
    }, 0)

    return answer
}
 ```
[올바른 괄호](https://school.programmers.co.kr/learn/courses/30/lessons/12909) (스택/큐)
  ```javascript
function solution(s){
   const stack = []

   for(let char of s){
        if(char === "(") {
            stack.push(char)
        } else {
            stack.at(-1) === "(" ? stack.pop() : stack.push(char)
        }
   }

    return !stack.length
}
 ```
[이진 변환 반복하기](https://school.programmers.co.kr/learn/courses/30/lessons/70129) (월간 코드 챌린지 시즌1)
  ```javascript
function solution(s) {
    let binary = s
    const answer = [0,0]

    while(binary !== "1"){
        answer[0] += 1
        answer[1] += binary.match(/0/g, '')?.length ?? 0
        binary = binary.replace(/0/g,'').length.toString(2)
    }

    return answer
}
 ```
[숫자의 표현](https://school.programmers.co.kr/learn/courses/30/lessons/12924) (연습 문제)
  ```javascript
function solution(n) {
    let answer = 0
    for(let i=1;i<=n+1;i++){
        if(n % i === 0 && i % 2 === 1) answer += 1
    }
    return answer
}
 ```
[다음 큰 숫자](https://school.programmers.co.kr/learn/courses/30/lessons/12911) (연습 문제)
  ```javascript
function solution(n) {
    let next = n + 1
    const count = n.toString(2).replace(/0/g, '').length
    while(count !== next.toString(2).replace(/0/g, '').length) next++

    return next
}
 ```
[피보나치 수](https://school.programmers.co.kr/learn/courses/30/lessons/12945) (연습 문제)
  ```javascript
function solution(n) {
    const f = [0,1]
    for(let i=2;i<=n;i++) f[i] = (f[i-1] + f[i-2]) % 1234567

    return f[n]
}
 ```
[짝지어 제거하기](https://school.programmers.co.kr/learn/courses/30/lessons/12973) (2017 팁스타운)
  ```javascript
function solution(s){
    const stack = []

    for(let str of s){
        stack.at(-1) === str ? stack.pop() : stack.push(str)
    }

    return stack.length === 0 ? 1 : 0 
}
 ```
[영어 끝말잇기](https://school.programmers.co.kr/learn/courses/30/lessons/12981) (Summer/Winter Coding(~2018))
  ```javascript
function solution(n, words) {
    const answer = [0,0]
    const pass = new Set([])
    let last

    words.some((word, i) => {
        if((last && last !== word[0]) || pass.has(word)){
            answer[0] = i % n + 1
            answer[1] = Math.floor(i / n + 1)
            return true
        }
        pass.add(word)
        last = word.at(-1)
    })

    return answer
}
 ```
[카펫](https://school.programmers.co.kr/learn/courses/30/lessons/42842) (완전탐색)
  ```javascript
function solution(brown, yellow) {
    const answer = []
    const size = brown + yellow

    for(let x=1;x<=size;x++){
        const y = size / x
        if(size % x === 0 && 2*(x + y - 2) + yellow === size){
            answer.push(x, y)
            break
        }
    }

    return answer.sort((a,b) => b-a)
}
 ```
[예상 대진표](https://school.programmers.co.kr/learn/courses/30/lessons/12985) (2017 팁스타운)
  ```javascript
function solution(n,a,b){
    let answer = 0

    while(a !== b){
        a = Math.round(a/2)
        b = Math.round(b/2)
        answer++
    }

    return answer
}
 ```
[구명보트](https://school.programmers.co.kr/learn/courses/30/lessons/42885) (탐욕법(Greedy))
  ```javascript
function solution(people, limit) {
    let answer = 0
    let i = 0
    let j = people.length - 1
    people.sort((a,b) => a-b)

    while(i <= j){
        if(people[i] + people[j] <= limit) i++
        j--
        answer++
    }

    return answer
}
 ```
[점프와 순간 이동](https://school.programmers.co.kr/learn/courses/30/lessons/12980) (Summer/Winter Coding(~2018))
  ```javascript
function solution(n){
    let answer = 0

    while(n){
        if(n % 2){
            n -= 1
            answer++
        } else n /= 2
    }

    return answer
}
 ```
[N개의 최소공배수](https://school.programmers.co.kr/learn/courses/30/lessons/12953) (연습 문제)
  ```javascript
function solution(arr) {
    let answer = arr[0]
    let gcd = arr[0]

    for(let i=0;i<arr.length-1;i++){
        let a = answer
        let b = arr[i+1]
        let r
        while(a % b){
            r = a % b
            a = b
            b = r
        }
        gcd = b
        answer *= arr[i+1] / gcd
    }

    return answer
}
 ```
[멀리 뛰기](https://school.programmers.co.kr/learn/courses/30/lessons/12914) (연습 문제)
  ```javascript
function solution(n) {
    const answer = [1,1,2]
    for(let i=0;i<= n;i++){
        answer[i+2] = (answer[i] + answer[i+1]) % 1234567
    }
    return answer[n] 
}
 ```
[귤 고르기](https://school.programmers.co.kr/learn/courses/30/lessons/138476) (연습 문제)
  ```javascript
function solution(k, tangerine) {
    let answer = 0
    let put = 0
    const sizes = tangerine.reduce((acc, cur) => {
        acc[cur] = acc[cur] ? acc[cur] + 1 : 1
        return acc
    }, {})    
    const count = Object.values(sizes).sort((a,b) =>b-a)
    for(let i=0;i<count.length;i++){
        if(put>=k) break
        put += count[i]
        answer++
    }

    return answer
}
 ```
[괄호 회전하기](https://school.programmers.co.kr/learn/courses/30/lessons/76502) (월간 코드 챌린지 시즌2)
  ```javascript
function solution(s) {
    let answer = 0
    const bracket = {
        "[": "]",
        "(": ")",
        "{": "}"
    }
    for(let i=0;i<s.length;i++){
        if(i){
            const temp = [...s]
            temp.push(temp.shift())
            s = temp.join("")
        }
        const stack = []
        for(let char of s){
            bracket[stack.at(-1)] === char ? stack.pop() : stack.push(char)
        }
        if(!stack.length) answer++
    }

    return answer
}
 ```
[H-Index](https://school.programmers.co.kr/learn/courses/30/lessons/42747) (정렬)
  ```javascript
function solution(citations) {
    citations.sort((a,b) => b-a)
    let answer = 0
    while(answer < citations[answer]) answer++

    return answer
}
 ```
[연속 부분 수열 합의 개수](https://school.programmers.co.kr/learn/courses/30/lessons/131701) (연습 문제)
  ```javascript
function solution(elements) {
   const answer = new Set([])

   for(let i=1;i<=elements.length;i++){
       for(let j=0;j<elements.length;j++){
           let sum = 0
            for(let k=j;k<j+i;k++){
                sum += elements[k%elements.length]
            }
           answer.add(sum)
       }
   }

    return answer.size
}
 ```
[n^2 배열 자르기](https://school.programmers.co.kr/learn/courses/30/lessons/87390) (월간 코드 챌린지 시즌3)
  ```javascript
function solution(n, left, right) {
    const arr = []
    for(let i=Math.floor(left/n);i<=Math.floor(right/n);i++){
        for(let j=0;j<n;j++){
           arr.push(j < i ? i+1 : j+1)
        }
    }
    return arr.slice(left%n,left%n+right-left+1)
}
 ```
[행렬의 곱셈](https://school.programmers.co.kr/learn/courses/30/lessons/12949) (연습 문제)
  ```javascript
function solution(arr1, arr2) {
    const answer = []
    for(let i=0;i<arr1.length;i++){
        const arr = []
        for(let j=0;j<arr2[0].length;j++){
            let sum = 0
            for(let k=0;k<arr2.length;k++){
                sum += arr1[i][k] * arr2[k][j]
            }
            arr.push(sum)
        }
        answer.push(arr)
    }
    
  return answer  
} 
 ```
[[1차] 캐시](https://school.programmers.co.kr/learn/courses/30/lessons/17680) (2018 KAKAO BLIND RECRUITMENT)
  ```javascript
function solution(cacheSize, cities) {
    let answer = 0
    const cache = []

    cities.forEach((cityName) => {
        const city = cityName.toUpperCase()
        const index = cache.indexOf(city)
        if(index > -1){
            cache.splice(index,1)
            answer += 1
        } else {
            if(cache.length === cacheSize) cache.shift()
            answer += 5
        }
        if(cacheSize) cache.push(city)
    })

    return answer
}
 ```
[의상](https://school.programmers.co.kr/learn/courses/30/lessons/42578) (해시)
  ```javascript
function solution(clothes) {
    const countByType = Object.values(clothes.reduce((acc, cur) => {
        acc[cur[1]] = acc[cur[1]] ? acc[cur[1]] + 1 : 1
        return acc
    },{}))

    return countByType.reduce((acc, cur) => acc *= (1+cur), 1) - 1
}
 ```
[튜플](https://school.programmers.co.kr/learn/courses/30/lessons/64065) (2019 카카오 개발자 겨울 인턴십)
  ```javascript
function solution(s) {
    const count = {}
    s.match(/[\d]+/g).forEach((char) => {
        count[char] = count[char] ? count[char] + 1 : 1
    })
    const entries = Object.entries(count).sort((a,b) => b[1]-a[1])    

    return entries.map((entrie) => Number(entrie[0]))
}
 ```
[할인 행사](https://school.programmers.co.kr/learn/courses/30/lessons/131127) (연습 문제)
  ```javascript
function solution(want, number, discount) {
    let answer = 0
    for(let i=0;i<discount.length-want.length;i++){
        const num = [...number]
        for(let j=i;j<i+10;j++){
            const index = want.indexOf(discount[j])
            if(num[index]) num[index]--
        }
        if(num.findIndex(n => !!n) === -1) answer++
    }

    return answer
}
 ```
[기능개발](https://school.programmers.co.kr/learn/courses/30/lessons/42586) (스택/큐)
  ```javascript
function solution(progresses, speeds) {
    const answer = []
    let last = 0
    progresses.forEach((progress, index) => {
        const day = Math.ceil((100-progress) / speeds[index])
        if(last < day) {
            answer.push(1)
            last = day
        } else answer[answer.length-1]++
    })

    return answer
}
 ```
[프로세스](https://school.programmers.co.kr/learn/courses/30/lessons/42587) (스택/큐)
  ```javascript
function solution(priorities, location) {
    let answer = 0

    while(priorities.length){
        const p = priorities.shift()
        location--
        if(priorities.findIndex(q => q > p) > -1){
            if(location === -1) location = priorities.length
            priorities.push(p)
        } else answer++
        if(location === -1) break
    }

    return answer
}
 ```
[[1차] 뉴스 클러스터링](https://school.programmers.co.kr/learn/courses/30/lessons/17677) (2018 KAKAO BLIND RECRUITMENT)
  ```javascript
function solution(str1, str2) {
    const set = (string) => {
        const arr = []
        const count = {}
        for(let i in string){
            if(+i === string.length-1) break
            const s = `${string[+i]}${string[+i+1]}`.toUpperCase()
            if(/^[A-Z]+$/.test(s)){
                arr.push(s)
                count[s] = count[s] ? count[s]+1 : 1
            }
        }
        return [arr, count]
    }
    const [arrA, countA] = set(str1)
    const [arrB, countB] = set(str2)
    const [intersection, union] = [...new Set([...arrA,...arrB])].reduce((acc, cur) => {
        for(let i=0;i<Math.min(countA[cur] ?? 0,countB[cur] ?? 0);i++) acc[0].push(cur)
        for(let i=0;i<Math.max(countA[cur] ?? 0,countB[cur] ?? 0);i++) acc[1].push(cur)
        return acc
        } , [[], []])

    const J = (intersection.length+union.length) ? intersection.length/union.length : 1
    
    return Math.floor(J * 65536)
}
 ```
[피로도](https://school.programmers.co.kr/learn/courses/30/lessons/87946) (완전탐색)
  ```javascript
function solution(k, dungeons) {
    const getPermutation = (arr, num) => {
        const results = []
        if(num === 1) return arr.map((el) => [el])
        arr.forEach((fixed, index, origin) => {
            const rest = [...origin.slice(0, index), ...origin.slice(index+1)]
            const permutations = getPermutation(rest, num-1)
            const attached = permutations.map((el) => [fixed, ...el])
            results.push(...attached)
        })
        return results
    }
    const indexArr = Array.from(Array(dungeons.length).keys())
    const permutation = getPermutation(indexArr, dungeons.length)

    let answer = 0
    permutation.forEach((list) => {
        let max = 0
        let fatigue = k
        list.some((index) => {
            if(fatigue < dungeons[index][0]) return true
            fatigue -= dungeons[index][1]
            max++
            if(max > answer) answer = max
        }) 
    })

    return answer
}
 ```
[타겟 넘버](https://school.programmers.co.kr/learn/courses/30/lessons/43165) (깊이/너비 우선 탐색(DFS/BFS))
  ```javascript
function solution(numbers, target) {
    let answer = 0
    function DFS(level, sum) {
        if (level === numbers.length) {
            if (sum === target) answer++
        } else {
            DFS(level+1, sum+numbers[level])
            DFS(level+1, sum-numbers[level])
        }
    }
    DFS(0, 0)

    return answer 
}
 ```
[k진수에서 소수 개수 구하기](https://school.programmers.co.kr/learn/courses/30/lessons/92335) (2022 KAKAO BLIND RECRUITMENT)
  ```javascript
function solution(n, k) {
    const arr = n.toString(k).split("0").filter((n) => n !== "" && n !== "0" && n !== "1")
    const answer = arr.filter(value => {
        let isPrime = true
        for(let i=2;i<=Math.sqrt(value);i++){
            if(!(value%i)) {
                isPrime = false 
                break
            }
        }
        return isPrime
    }).length

    return answer
}
 ```
[[3차] 압축](https://school.programmers.co.kr/learn/courses/30/lessons/17684) (2018 KAKAO BLIND RECRUITMENT)
  ```javascript
function solution(msg) {
    const answer = []
    const dictionary = new Map()
    const alphabet = "ABCDEFGHIJKLMNOPQRSTUVWXYZ"
    for(let i in alphabet) dictionary.set(alphabet[i],+i+1)

    while(msg.length){
        let w = ""
        for(let i=1;i<=msg.length;i++){
            const str = msg.slice(0,i)
            if(!dictionary.has(str)) break
            w = str
        }
        msg = msg.slice(w.length)
        answer.push(dictionary.get(w))
        dictionary.set(w+msg[0], dictionary.size+1)
    }

    return answer
}
 ```
[[3차] n진수 게임](https://school.programmers.co.kr/learn/courses/30/lessons/17687) (2018 KAKAO BLIND RECRUITMENT)
  ```javascript
function solution(n, t, m, p) {
    let answer = ''
    let str = ''

    for(let i=0;i<t*m;i++) str += i.toString(n)
    for(let i=0;i<t;i++) answer += str[m*i+p-1]

    return answer.toUpperCase()
}
 ```
[주차 요금 계산](https://school.programmers.co.kr/learn/courses/30/lessons/92341) (2022 KAKAO BLIND RECRUITMENT)
  ```javascript
function solution(fees, records) {
    const timesByCar = records.reduce((acc, cur) => {
        const licensePlate = cur.slice(6,10)
        const time = cur.slice(0,5)
        acc[licensePlate] =  acc[licensePlate] ? [...acc[licensePlate], time]  : [time]
        return acc
    }, {})
    const feeByCar = {}
    for(let licensePlate in timesByCar){
        const fee = timesByCar[licensePlate].reduce((acc, cur, index, origin) => {
            if(index%2) return acc
            const [inHour, inSecond] = cur.split(":")
            const [outHour, outSecond] = origin[index+1] ? origin[index+1].split(":") : [23,59] 
            return acc += (outHour-inHour)*60 + (outSecond-inSecond)
        }, 0)        
        const condition = fee <= fees[0] ? 0 : Math.ceil((fee-fees[0])/fees[2])*fees[3]
        feeByCar[licensePlate] = fees[1] + condition
    }

    return Object.entries(feeByCar).sort((a,b) => a[0]-b[0]).map(a => a[1])
}
 ```
[전화번호 목록](https://school.programmers.co.kr/learn/courses/30/lessons/42577) (해시)
  ```javascript
function solution(phone_book) {
    return !phone_book.sort().some((phone, i) => {
        if(phone_book[i+1]) return phone_book[i+1].startsWith(phone)
    })
} 
 ```
