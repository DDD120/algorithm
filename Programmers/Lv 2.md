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
