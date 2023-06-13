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
