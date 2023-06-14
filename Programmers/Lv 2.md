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
