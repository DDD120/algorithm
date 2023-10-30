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
[더 맵게](https://school.programmers.co.kr/learn/courses/30/lessons/42626) (힙(Heap))
  ```javascript
class MinHeap {
    constructor() {
        this.heap = []
    }
    size() {
        return this.heap.length
    }
    getParentIndex(childIndex) {
        return Math.floor((childIndex-1) / 2)
    }
    getLeftChildIndex(parentIndex) {
        return parentIndex*2 + 1
    }
    getRightChildIndex(parentIndex) {
        return parentIndex*2 + 2
    }
    swap(index1, index2){
        [this.heap[index1], this.heap[index2]] = [this.heap[index2], this.heap[index1]]
        return this.heap
    }
    heappop(){
        const heapSize = this.size()
        if (!heapSize) return null
        if (heapSize === 1) return this.heap.pop()
        const value = this.heap[0]
        this.heap[0] = this.heap.pop()
        this.bubbledown()
        return value
    }
    heappush(value){
        this.heap.push(value)
        this.bubbleup()
    }
    bubbleup(){
        let child = this.size()-1
        let parent = this.getParentIndex(child)
        while(this.heap[child] < this.heap[parent]){
            this.swap(child, parent)
            child = parent
            parent = this.getParentIndex(parent)
        }
    }
    bubbledown(){
        let parent = 0
        let leftChild = this.getLeftChildIndex(parent)
        let rightChild = this.getRightChildIndex(parent)
        while((leftChild <= this.size()-1 && this.heap[leftChild] < this.heap[parent]) || 
              (rightChild <= this.size()-1 && this.heap[rightChild] < this.heap[parent])){
            if (rightChild <= this.size()-1 && this.heap[leftChild] > this.heap[rightChild]){
                this.swap(parent, rightChild)
                parent = rightChild
            } else {
                this.swap(parent, leftChild)
                parent = leftChild
            }
            leftChild = this.getLeftChildIndex(parent)
            rightChild = this.getRightChildIndex(parent)
        }     
    }
}

function solution(scoville, K) {
    let answer = 0
    const h = new MinHeap()
    scoville.forEach(s => h.heappush(s))

    while(h.heap[0] < K && h.size() > 1){
        h.heappush(h.heappop() + (h.heappop() * 2))
        answer++
    }

    return h.heap[0] >= K ? answer : -1
}
 ```

[오픈채팅방](https://school.programmers.co.kr/learn/courses/30/lessons/42888) (2019 KAKAO BLIND RECRUITMENT)
 ```javascript
function solution(record) {
    const answer = []
    const map = record.reduce((acc, cur) => {
        const [act, id, nickname] = cur.split(' ')
        if(nickname) acc[id] = nickname
        return acc
    }, {})

    record.forEach(r => {
        const [act, id] = r.split(' ')
        if(act === "Enter") answer.push(map[id] + "님이 들어왔습니다.")
        if(act === "Leave") answer.push(map[id] + "님이 나갔습니다.")
    })

    return answer
}
 ```
[땅따먹기](https://school.programmers.co.kr/learn/courses/30/lessons/12913) (연습문제)
 ```javascript
function solution(land) {
    for(let i=0;i<land.length-1;i++){
        land[i+1][0] += Math.max(land[i][1], land[i][2], land[i][3])
        land[i+1][1] += Math.max(land[i][0], land[i][2], land[i][3])
        land[i+1][2] += Math.max(land[i][0], land[i][1], land[i][3])
        land[i+1][3] += Math.max(land[i][0], land[i][1], land[i][2])
    }

    return Math.max(...land.at(-1))
}
 ```
[주식가격](https://school.programmers.co.kr/learn/courses/30/lessons/42584) (스택/큐)
 ```javascript
function solution(prices) {
    const answer = []
    for(let i=0;i<prices.length;i++){
        let seconds = prices.length-i-1
        for(let j=i+1;j<prices.length-1;j++){
            if(prices[j] < prices[i]) {
                seconds = j-i
                break
            }
        }
        answer.push(seconds)
    }

    return answer
}
 ```
[게임 맵 최단거리](https://school.programmers.co.kr/learn/courses/30/lessons/1844) (깊이/너비 우선 탐색(DFS/BFS))
 ```javascript
function solution(maps) {
    const queue = [[0,0]]
    const move = [[1,0],[0,1],[0,-1],[-1,0]]
    const [n,m] = [maps.length-1, maps[0].length-1]
    while(queue.length){
        if(maps[n][m] > 1) break
        const [nowY, nowX] = queue.shift()
        for(let i=0;i<4;i++){
            const [nextY, nextX] = [nowY+move[i][0], nowX+move[i][1]]
            if(maps[nextY]?.[nextX] === 1){
                maps[nextY][nextX] = maps[nowY][nowX] + 1
                queue.push([nextY,nextX])
           }
        }
    }

    return maps[n][m] === 1 ? -1 : maps[n][m]
}
 ```
[방문 길이](https://school.programmers.co.kr/learn/courses/30/lessons/49994) (Summer/Winter Coding(~2018))
 ```javascript
function solution(dirs) {
    let answer = 0
    const move = [[0,0]]
    for(let char of dirs){
        const [x,y] = move.at(-1)
        if(char === "U") if(y+1 <= 5) move.push([x,y+1])
        if(char === "D") if(y-1 >= -5) move.push([x,y-1])
        if(char === "R") if(x+1 <= 5) move.push([x+1,y])
        if(char === "L") if(x-1 >= -5) move.push([x-1,y])
    }
    for(let i=0;i<move.length-1;i++){
        const way1 = move.slice(i,i+2).sort()
        let pass = true
        for(let j=0;j<i;j++){
            const way2 = move.slice(j,j+2).sort()
            const condition = way1[0][0] == way2[0][0] && 
                  way1[0][1] == way2[0][1] && 
                  way1[1][0] == way2[1][0] && 
                  way1[1][1] == way2[1][1]
            if(condition) pass = false
        }
        if(pass) answer += 1
    }

   return answer
}
 ```
[스킬트리](https://school.programmers.co.kr/learn/courses/30/lessons/49993) (Summer/Winter Coding(~2018))
 ```javascript
function solution(skill, skill_trees) {
    let answer = 0
     skill_trees.forEach(tree => {
         const regexp = new RegExp(`[^${skill}]+`, 'g')
         if(skill.startsWith(tree.replace(regexp, ''))) answer++
     })

    return answer
}
 ```
[모음사전](https://school.programmers.co.kr/learn/courses/30/lessons/84512) (완전탐색)
 ```javascript
function solution(word) {
    let answer = 0
    const score = { 'A': 0,'E': 1,'I': 2,'O': 3,'U': 4 }
    for(let i=0;i<word.length;i++){
        answer += score[word[i]] * ((5**(5-i)-1)/4) + 1
    }

    return answer
}
 ```
[뒤에 있는 큰 수 찾기](https://school.programmers.co.kr/learn/courses/30/lessons/154539) (연습문제)
 ```javascript
function solution(numbers) {
    const answer = []
    const stack = []
    for(let i=0;i<numbers.length;i++){
        while(stack.length && numbers[stack.at(-1)] < numbers[i]){
                answer[stack.pop()] = numbers[i]
        }
        stack.push(i)
    }
    stack.forEach((i) => answer[i] = -1)

    return answer
}
 ```
[[3차] 파일명 정렬](https://school.programmers.co.kr/learn/courses/30/lessons/17686) (2018 KAKAO BLIND RECRUITMENT)
 ```javascript
function solution(files) {
    files.sort((a,b) => {
        a = a.toLowerCase().match(/([a-z-\s.]+|\d+)/g)
        b = b.toLowerCase().match(/([a-z-\s.]+|\d+)/g)
        if(a[0] < b[0]) return -1
        if(a[0] > b[0]) return 1
        if(+a[1] < +b[1]) return -1
        if(+a[1] > +b[1]) return 1
    })
    return files
}
 ```
[[1차] 프렌즈4블록](https://school.programmers.co.kr/learn/courses/30/lessons/17679) (2018 KAKAO BLIND RECRUITMENT)
 ```javascript
function solution(m, n, board) {
    let answer = 0
    board = board.map((b) => b.split(''))
    while(true){
        const same = Array.from(new Array(m), () => new Array(n).fill(false))
        board.forEach((b, x) => {
            for(let y in b){
                if(b[y] !== ' ' && 
                   b[y] === b[+y+1] && 
                   b[y] === board[x+1]?.[y] &&
                   b[y] === board[x+1]?.[+y+1]){
                    same[x][y] = true
                    same[x][+y+1] = true
                    same[x+1][y] = true
                    same[x+1][+y+1] = true
                }
            } 
        })
        if(!same.flat().some((n) => n)) break
        same.forEach(s => s.forEach((b) => { if(b) answer += 1 }))
        board.forEach((b, index) => { for(let i in b) if(same[index][i]) b[i] = ' ' })
        for(let re=0;re<m-1;re++){
            for(let x=0;x<m-1;x++){
                for(let y=0;y<n;y++){
                    if(board[x][y] !== ' ' && board[x+1][y] === ' '){
                        board[x+1][y] = board[x][y]
                        board[x][y] = ' '
                    } 
                }
            }
        }
    }

    return answer
}
 ```
[롤케이크 자르기](https://school.programmers.co.kr/learn/courses/30/lessons/132265) (연습문제)
 ```javascript
function solution(topping) {
    let answer = 0
    const left = new Map()
    const right = new Map()
    topping.forEach(t => right.set(t, right.get(t) ? right.get(t)+1 : 1))
    topping.forEach(t => {
        right.set(t, right.get(t)-1)
        if(!right.get(t)) right.delete(t)
        left.set(t, left.get(t) ? left.get(t)+1 : 1)
        if(left.size === right.size) answer++
    })

    return answer
}
 ```
[숫자 변환하기](https://school.programmers.co.kr/learn/courses/30/lessons/154538) (연습문제)
 ```javascript
function solution(x, y, n) {
    let answer = -1
    const queue = [[y, 0]]
    while(queue.length){
        const [y, num] = queue.shift()
        if(x === y){
            answer = num
            break
        }
        if(y % 2 === 0) queue.push([y/2, num+1]) 
        if(y % 3 === 0) queue.push(([y/3, num+1])) 
        if(y - n >= x) queue.push([y-n, num+1]) 
    }

    return answer
}
 ```
[2 x n 타일링](https://school.programmers.co.kr/learn/courses/30/lessons/12900) (연습문제)
 ```javascript
function solution(n) {
  const f = [1,1]
  for(let i=2;i<=n;i++) f[i] = (f[i-1] + f[i-2]) % 1000000007

  return f[n]
}
 ```
[2개 이하로 다른 비트](https://school.programmers.co.kr/learn/courses/30/lessons/77885) (월간 코드 챌린지 시즌2)
 ```javascript
function solution(numbers) {
    return numbers.map(number => {
        if(number % 2 === 0) return number+1
        else {
            const b = number.toString(2).padStart(32,0).split('')
            b.splice(b.lastIndexOf('0'),2,1,0)
            return parseInt(b.join(''), 2)
        }
    })
}
 ```
[다리를 지나는 트럭](https://school.programmers.co.kr/learn/courses/30/lessons/42583) (스택/큐)
 ```javascript
function solution(bridge_length, weight, truck_weights) {
    let answer = 1
    const queue = [[truck_weights.shift(), 1]]
    let currentWeight = queue[0][0]

    while(queue.length){
        while(queue[0]?.[1] >= bridge_length){
            currentWeight -= queue[0][0]
            queue.shift()
        }
        const truck = truck_weights[0]
        if(queue.length <= bridge_length && currentWeight + truck <= weight){
            currentWeight += truck
            queue.push([truck_weights.shift(), 0])
        }
        queue.forEach(q => q[1] = q[1]+1)
        answer++
    }

    return answer
}
 ```
[택배상자](https://school.programmers.co.kr/learn/courses/30/lessons/131704) (연습문제)
 ```javascript
function solution(order) {
    let answer = 0
    const belt = Array.from({length: order.length}, (_,i) => order.length-i)
    const assistant = []

    for(let i in order){
        while(true){
            if(order[i] === belt.at(-1)){
                answer++
                belt.pop()
                break
            } else if(order[i] === assistant.at(-1)){
                answer++
                assistant.pop()
                break
            } else assistant.push(belt.pop())
            if(!belt.length && order[i] !== assistant.at(-1)) break
        }
    }

    return answer
}
 ```
[가장 큰 수](https://school.programmers.co.kr/learn/courses/30/lessons/42746) (정렬)
 ```javascript
function solution(numbers) {
    numbers.sort((a,b) => {
        a = a.toString(), b = b.toString()
        return (a+b) > (b+a) ? -1 : 1
    })
    const answer = numbers.join('')
    return +answer ? answer : '0'
}
 ```
[소수 찾기](https://school.programmers.co.kr/learn/courses/30/lessons/42839) (완전탐색)
 ```javascript
function solution(numbers) {
    numbers = numbers.split('')
    const getPermutations = (arr, num) => {
        const results = []
        if (num === 1) return arr.map(el => el);
        arr.forEach((fixed, index, origin) => {
          const rest = [...origin.slice(0, index), ...origin.slice(index+1)] 
          const permutations = getPermutations(rest, num-1)
          const attached = permutations.map(el => fixed+el)
          results.push(...attached)
        })
        return results
    }
    const permutations = []
    for(let i in numbers) permutations.push(...getPermutations(numbers, +i+1))
    let answer = 0
    new Set(permutations.map(p => +p)).forEach(p => {
        let isPrime = true
        if(p === 0 || p === 1) isPrime = false
        for(let i=2;i<=p/2;i++){
            if(p % i === 0){
                isPrime = false
                break
            }
        }
        if(isPrime) answer += 1
    })

    return answer
}
 ```
[쿼드압축 후 개수 세기](https://school.programmers.co.kr/learn/courses/30/lessons/68936) (월간 코드 챌린지 시즌1)
 ```javascript
function solution(arr) {
    const answer = [0,0]
    function quad(arr, len){
        if(arr.flat().every(cell => cell === 0)) return answer[0]++
        if(arr.flat().every(cell => cell === 1)) return answer[1]++
        quad(arr.slice(0, len/2).map(row => row.slice(0, len/2)), len/2)
        quad(arr.slice(0, len/2).map(row => row.slice(len/2)), len/2)
        quad(arr.slice(len/2).map(row => row.slice(0, len/2)), len/2)
        quad(arr.slice(len/2).map(row => row.slice(len/2)), len/2)
    }
    quad(arr, arr.length)
    return answer
}
 ```
[삼각 달팽이](https://school.programmers.co.kr/learn/courses/30/lessons/68645) (월간 코드 챌린지 시즌1)
 ```javascript
function solution(n) {
    const answer = []
    let x = 0, y = 0, index = 1
    for(let i=0;i<n;i++) answer.push(new Array(i+1).fill(0))
    while(index <= (n/2+0.5)*n){
        while(x < n && !answer[x][y]) answer[x++][y] = index++
        x--
        y++
        while(y < n && !answer[x][y]) answer[x][y++] = index++
        x--
        y-= 2
        while(x > 0 && y > 0 && !answer[x][y]) answer[x--][y--] = index++
        x += 2
        y += 1
    }
    return answer.flat()
}
 ```
[큰 수 만들기](https://school.programmers.co.kr/learn/courses/30/lessons/42883) (탐욕법(Greedy))
 ```javascript
function solution(number, k) {
    const num = number.split('').reverse()
    const answer = [num.pop()]
    let index = 0
    while(num.length){
        while(index < k && answer.at(-1) < num.at(-1)){
            answer.pop()
            index++
        }
        answer.push(num.pop())
    }
    const len = k - (number.length - answer.length)
    for(let i=0;i<len;i++) answer.pop()
    
    return answer.join('')
}
 ```
[124 나라의 숫자](https://school.programmers.co.kr/learn/courses/30/lessons/12899) (연습문제)
 ```javascript
function solution(n) {
    const answer = []
    while(n !== 0){
        const quotient = Math.floor(n / 3)
        const remainder = n % 3
        answer.push(remainder === 0 ? 4 : remainder)
        n = remainder === 0 ? quotient - 1 : quotient
    }

    return answer.reverse().join('')
}
 ```
[두 큐 합 같게 만들기](https://school.programmers.co.kr/learn/courses/30/lessons/118667) (2022 KAKAO TECH INTERNSHIP)
 ```javascript
function solution(queue1, queue2) {
    let answer = 0
    let index1 = 0, index2 = 0
    let sum1 = queue1.reduce((acc, cur) => acc += cur , 0)
    let sum2 = queue2.reduce((acc, cur) => acc += cur , 0)
    const condition =  (queue1.length + queue2.length) * 3

    while(sum1 !== sum2){
        if(answer > condition){
            answer = -1
            break 
        }
        if(sum1 > sum2){
            const num = queue1[index1]
            index1++
            queue2.push(num)
            sum1 -= num
            sum2 += num
        } else {
            const num = queue2[index2]
            index2++
            queue1.push(num)
            sum1 += num
            sum2 -= num
        }
        answer++
    }

    return answer
}
 ```
[연속된 부분 수열의 합](https://school.programmers.co.kr/learn/courses/30/lessons/178870) (연습문제)
 ```javascript
function solution(sequence, k) {
    const sumSequence = []
    for(let s of sequence) sumSequence.push((sumSequence.at(-1) ?? 0) + s)
    let answer
    let left = 0, right = 0
    while(left <= right){
        const sum = sumSequence[right]-(sumSequence[left-1] ?? 0)
        if(sum === k) {
            if(!answer || right-left < answer[1]-answer[0]) {
                answer = [left, right]
            }
        }
        sum < k ? right++ : left++
    }

    return answer
}
 ```
[메뉴 리뉴얼](https://school.programmers.co.kr/learn/courses/30/lessons/72411) (2021 KAKAO BLIND RECRUITMENT)
 ```javascript
function solution(orders, course) {
    function getCombination(arr, num){
        const results = []
        if(num === 1) return arr.map(el => [el])
        arr.forEach((fixed, index, origin) => {
            const rest = origin.slice(index+1)
            const combin = getCombination(rest, num-1)
            const attached = combin.map((c) => [fixed, ...c].sort().join(''))
            results.push(...attached) 
        })
        return results
    }
    const combins = new Set(orders.reduce((acc, cur) => {
        for(let i of course) acc.push(...getCombination(cur.split(''), i))
        return acc
    }, []))

    const orderCount = new Map()
    combins.forEach(combin => {
        const combinArray = combin.split('')
        orders.forEach(order => {
            if(combinArray.every(c => order.includes(c))) {
                const getCombin = orderCount.get(combin)
                orderCount.set(combin, getCombin ? getCombin + 1 : 1)
            }
        })
    })

    const rank = [...orderCount.entries()].filter((r) => r[1] > 1).sort((a,b) =>b[1]-a[1])
    const regular = new Map()
    rank.forEach((r) => {
        const courseCount = r[0].length
        if((regular.get(courseCount)?.[0][1] ?? 0) <= r[1]){
            if(regular.get(courseCount)?.[0][1] === r[1]){
                return regular.set(courseCount, [...regular.get(courseCount),r])
            }
            regular.set(courseCount, [r])
        }
    })
    const answer = []
    for(let value of regular.values()) answer.push(...value.map((v) => v[0]))

    return answer.sort()
}
 ```
[무인도 여행](https://school.programmers.co.kr/learn/courses/30/lessons/154540) (연습문제)
 ```javascript
function solution(maps) {
    maps = maps.map(map => map.split(''))
    const answer = []
    const dir = [[-1,0], [0,1], [1,0], [0,-1]]

    const [row, col] = [maps.length-1,maps[0].length-1]
    for (let i=0;i<=row;i++) {
        for (let j=0;j<=col;j++) {
            let square = maps[i][j]
            if (square === 'X') continue
            maps[i][j] = 'X'
            square = +square
            const queue = [[i, j]]
            while(queue.length){
                const [r, c] = queue.shift()
                for(let i=0;i<4;i++) {
                    const [nr, nc] = [r + dir[i][0], c + dir[i][1]]
                    if (0 > nr || nr > row || 0 > nc || nc > col) continue
                    const ns = maps[nr][nc]
                    if (ns === 'X') continue
                    maps[nr][nc] = 'X'
                    square += +ns
                    queue.push([nr, nc])
                }
            }
            answer.push(square)
        }
    }

    return answer.length ? answer.sort((a,b) => a-b) : [-1]
}
 ```
[[3차] 방금그곡](https://school.programmers.co.kr/learn/courses/30/lessons/17683) (2018 KAKAO BLIND RECRUITMENT)
 ```javascript
function solution(m, musicinfos) {
    let answer
     m = m.replace(/(C|D|F|G|A)#/g, (_, s) => s.toLowerCase())
    musicinfos.forEach((musicinfo) => {
        const [start, end, title, score] = musicinfo.split(',')
        const hour = end.slice(0,2)-start.slice(0,2)
        const playingTime = (hour*60 + +(end.slice(3,5)))-start.slice(3,5)
        const rScore = score.replace(/(C|D|F|G|A)#/g, (_, s) => s.toLowerCase())
        const playingScore = ''.padEnd(playingTime, rScore)
        const regexp = new RegExp(`${m}(?!#)`)
        const index = playingScore.match(regexp)?.index
        if(index > -1 && playingScore[index+m.length] !== '#'){
            if((answer?.[1] ?? 0) < playingTime) answer = [title, playingTime]
        }
    })

    return answer ? answer[0] : "(None)"
}
 ```
[괄호 변환](https://school.programmers.co.kr/learn/courses/30/lessons/60058) (2020 KAKAO BLIND RECRUITMENT)
 ```javascript
function isValid(u){
    const stack = [u[0]]
    for(let i=1;i<u.length;i++){
        if(stack.at(-1) === "(" && u[i] === ")") stack.pop() 
        else stack.push(u[i])
    }
    return stack.length ? false : true
}

function solution(p){
    function setValidParentheses(w){
        if(w === "") return ""
        let u = ""
        let [left, right] = [0,0]
        for(let i=0;i<w.length;i++){
            if(w[i] === "("){
                left++
                u+= "("
            } else {
                right++
                u+= ")"
            }
            if(left === right) break
        }
        const v = w.slice(u.length)
        const join = setValidParentheses(v)
        if(isValid(u)) return u + join
        else {
            const s = [...u.slice(1,u.length-1)]
                .map((char) => char === "(" ? ")" : "(").join("")
            return `(${join})` + s
        }
        return v
    }

    return setValidParentheses(p)
}
 ```
[전력망을 둘로 나누기](https://school.programmers.co.kr/learn/courses/30/lessons/86971) (완전탐색)
 ```javascript
function solution(n, wires) {
    let answer = n
    wires.forEach((wire) => {
        const except = wires.filter((w) => w !== wire)
        const A = [wire[0]]
        const B = [wire[1]]
        while(except.length){
            const wire = except.shift()
            if(wire.some(w => A.includes(w))) A.push(...wire)
            else if(wire.some(w => B.includes(w))) B.push(...wire)
            else except.push(wire)
        }
        const diff = Math.abs(new Set(A).size - new Set(B).size)
        if(diff < answer) answer = diff
    })

    return answer
}
 ```
[수식 최대화](https://school.programmers.co.kr/learn/courses/30/lessons/67257) (2020 카카오 인턴십)
 ```javascript
function solution(expression) {
    const combination = ['+-*', '-+*', '+*-', '-*+', '*+-', '*-+']
    const answer = combination.map(combin => {
        const exp = expression.match(/\d+|\D/g)
        for(let c of combin){
            while(exp.includes(c)){
                const index = exp.indexOf(c)
                let calc
                if(c === '+') calc = +exp[index-1] + +exp[index+1]
                if(c === '-') calc = exp[index-1] - exp[index+1]
                if(c === '*') calc = exp[index-1] * exp[index+1]
                exp.splice(index-1, 3, calc)
            }
        }
        return Math.abs(exp[0])
    })

    return Math.max(...answer)
}
 ```
[행렬 테두리 회전하기](https://school.programmers.co.kr/learn/courses/30/lessons/77485) (2021 Dev-Matching: 웹 백엔드 개발자(상반기))
 ```javascript
function solution(rows, columns, queries) {
    const matrix = []
    for(let index=0;index<rows;index++){
        matrix.push(Array.from({length: columns},(_,i)=>(i+1)+(columns*index)))
    }
    const answer = queries.map((q) => {
        const [x1,y1,x2,y2] = [--q[0],--q[1],--q[2],--q[3]]
        let min = matrix[x1][y1]
        let prev = matrix[x1][y1]
        function move(x,y){
            const temp = matrix[x][y]
            matrix[x][y] = prev
            if(prev < min) min = prev 
            prev = temp
        }
        for(let i=0;i<y2-y1;i++) move(x1,y1+i+1)
        for(let i=0;i<x2-x1;i++) move(x1+i+1,y2)
        for(let i=0;i<y2-y1;i++) move(x2,y2-i-1)
        for(let i=0;i<x2-x1;i++) move(x2-i-1,y1)

        return min
    })

    return answer
}
 ```
[호텔 대실](https://school.programmers.co.kr/learn/courses/30/lessons/155651) (연습 문제)
 ```javascript
function solution(book_time) {
    const rooms = []
    const time = (s) => +s.slice(0,2)*60 + +s.slice(3,5)
    book_time = book_time.map(book => [time(book[0]),time(book[1])+10])
        .sort((a,b) => a[0]-b[0] || a[1]-b[1])
    book_time.forEach(book => {
        let index
        const isValid = rooms.some((room, i) => {
            if(room.at(-1)[1] <= book[0]){
                index = i
                return true
            }
        })
        isValid ? rooms[index].push(book) : rooms.push([book])
    })

    return rooms.length
}
 ```
[줄 서는 방법](https://school.programmers.co.kr/learn/courses/30/lessons/12936) (연습 문제)
 ```javascript
function solution(n, k) {
    const answer = []
    const factorial = (n) => n === 0 || n === 1 ? 1 : n * factorial(n-1)
    const num = Array.from({ length: n }, (_, i) => i + 1)
    for(let i=0;i<n;i++){
        const index = Math.ceil(k / factorial(num.length-1)) - 1
        k = k % factorial(num.length-1)
        answer.push(num.splice(index,1)[0])
    }

    return answer
}
 ```
[배달](https://school.programmers.co.kr/learn/courses/30/lessons/12978) (Summer/Winter Coding(~2018))
 ```javascript
function solution(N, road, K) {
    const graph = Array.from({ length: N }, () => new Array(N).fill(500000))
    road.forEach(([t1,t2,time]) => {
        if(graph[t1-1][t2-1] > time) graph[t1-1][t2-1] = time
        if(graph[t2-1][t1-1] > time) graph[t2-1][t1-1] = time
    })
    const times = [...graph[0]]
    const visited = new Array(N).fill(false)
    visited[0] = true
    for(let i=0;i<N;i++){
        let current = 0
        let min = 500000
        for(let j=0;j<N;j++){
            if(!visited[j] && times[j] < min){
                min = times[j]
                current = j
            }
        }
        visited[current] = true
        for(let j=0;j<N;j++){
            if(!visited[j]){
                const time = times[current] + graph[current][j]
                if(time < times[j]){
                    times[j] = time
                }
            }
        }
    }

    return times.filter(time => time <= K).length + 1
}
 ```
[숫자 카드 나누기](https://school.programmers.co.kr/learn/courses/30/lessons/135807) (연습 문제)
 ```javascript
function solution(arrayA, arrayB) {
    let answer = 0
    function getMultipleGCD(numbers) {
        let gcd = numbers[0]
        function getGCD(a, b) {
          while (b) {
            const temp = b
            b = a % b
            a = temp
          }
          return a
        }
        for(let i=1;i<numbers.length;i++) gcd = getGCD(gcd, numbers[i])
        return gcd
    }
    const a = getMultipleGCD(arrayA)
    if(arrayB.every(n => n % a)) answer = a
    const b = getMultipleGCD(arrayB)
    if(arrayA.every(n => n % b) && answer < b) answer = b

    return answer
}
 ```
[시소 짝꿍](https://school.programmers.co.kr/learn/courses/30/lessons/152996) (연습 문제)
 ```javascript
function solution(weights) {
    let answer = 0
    const dict = {}
    for(let weight of weights) dict[weight] = dict[weight] ? dict[weight]+1 : 1
    weights.sort((a,b) => a-b)
    for(let weight of weights){
        if(dict[weight] > 1) answer += (dict[weight]-1)
        answer += (dict[weight*2] ?? 0)
        answer += (dict[weight*(3/2)] ?? 0)
        answer += (dict[weight*(4/3)] ?? 0)
        dict[weight]--
    }

    return answer
}
 ```
[가장 큰 정사각형 찾기](https://school.programmers.co.kr/learn/courses/30/lessons/12905) (연습 문제)
 ```javascript
function solution(board){
    if(board.every(row => row.every(b => !b))) return 0
    let answer = 1
    for(let i=1;i<board.length;i++){
        for(let j=1;j<board[0].length;j++){
            if(!board[i][j]) continue
            const min = Math.min(board[i-1][j],board[i][j-1],board[i-1][j-1])
            board[i][j] = min + 1
            if(answer < board[i][j]) answer = board[i][j]
        }
    }

    return answer * answer
} 
 ```
[거리두기 확인하기](https://school.programmers.co.kr/learn/courses/30/lessons/81302) (2021 카카오 채용연계형 인턴십)
 ```javascript
function solution(places) {
    const moves = [[-1,0],[0,1],[1,0],[0,-1]]
    const answer = places.map(place => {
        let valid = 1
        for(let i=0;i<5;i++){
            if(!valid) break
            for(let j=0;j<5;j++){
                if(!valid) break
                if(place[i][j] !== 'P') continue
                const visited = Array.from({length:5}, () => new Array(5).fill(false))
                function explore(distance, pos){
                    let [y,x] = pos
                    if(distance > 2 || y < 0 || y > 4 || x < 0 || x > 4) return
                    if(place[y][x] === 'X') return
                    visited[y][x] = true
                    if(distance && place[y][x] === 'P') return valid = 0
                    moves.forEach(move => {
                        const [my, mx] = move
                        if(!visited[y+my]?.[x+mx]) explore(distance+1, [y+my,x+mx])
                    })
                }
                explore(0, [i,j])
            }
        }
        return valid
    })
    return answer
}
 ```
[점 찍기](https://school.programmers.co.kr/learn/courses/30/lessons/140107) (연습 문제)
 ```javascript
function solution(k, d) {
    let answer = 0
    for(let x=0;x<=d;x+=k){
        answer += Math.floor(Math.sqrt(d**2-x**2)/k) + 1
    }
    
    return answer
}
 ```
[멀쩡한 사각형](https://school.programmers.co.kr/learn/courses/30/lessons/62048) (Summer/Winter Coding(2019))
 ```javascript
function solution(w, h) {
    let count = 0
    for(let x=1;x<=w;x++) {
        count += Math.ceil(h*(x+1)/w) - Math.floor(h*x/w)
    }

    return w*h-count
}
 ```
[테이블 해시 함수](https://school.programmers.co.kr/learn/courses/30/lessons/147354) (연습 문제)
 ```javascript
function solution(data, col, row_begin, row_end) {
    let answer = 0
    data.sort((a,b) => a[col-1]-b[col-1] || b[0]-a[0])
    for(let i=row_begin;i<=row_end;i++){
        answer = answer ^ data[i-1].reduce((acc, cur) => acc += cur % i, 0) 
    }

    return answer
}
 ```
[미로 탈출](https://school.programmers.co.kr/learn/courses/30/lessons/159993) (연습 문제)
 ```javascript
function solution(maps) {
    const [maxY, maxX] = [maps.length, maps[0].length]
    function findPosition (char) {
        let result
        for(let y=0;y<maxY;y++){
            for(let x=0;x<maxX;x++){
                if(maps[y][x] === char) {
                    result = [y,x]
                    break
                }
            }
        }
        return result
    }
    const sPos = findPosition('S')
    const lPos = findPosition('L')

    const move = [[-1,0], [0,1], [1,0], [0,-1]]
    function BFS([y,x],char){
        let result = 0
        const visited = Array.from({length: maxY}, () => new Array(maxX).fill(false))
        const queue = [[y, x, 0]]
        visited[y][x] = true

        while(queue.length){
            const [y, x, count] = queue.shift()
            if(maps[y][x] === char) {
                result = count
                break
            }
            move.forEach((m) => {
                const [my, mx] = [y+m[0], x+m[1]]
                if(my < 0 || my >= maxY || mx < 0 || mx >= maxX) return
                if(maps[my][mx] === 'X') return
                if(!visited[my][mx]) {
                    queue.push([my, mx, count+1])
                    visited[my][mx] = true
                }
            })
        }

        return result
    }
    const s = BFS(sPos, 'L')
    const l = BFS(lPos, 'E')
    if(s === 0 || l === 0) return -1

    return s + l
}
 ```
[하노이의 탑](https://school.programmers.co.kr/learn/courses/30/lessons/12946) (연습 문제)
 ```javascript
function solution(n) {
    const answer = []
    const move = (n, from, mid, to) => {
        if(n === 1) return answer.push([from, to])
        move(n-1, from, to, mid);
        answer.push([from, to])
        move(n-1, mid, from, to)
    }
    move(n, 1, 2, 3)

    return answer
}
 ```
[문자열 압축](https://school.programmers.co.kr/learn/courses/30/lessons/60057) (2020 KAKAO BLIND RECRUITMENT)
 ```javascript
function solution(s) {
    let answer = s.length
    for(let i=1;i<=s.length/2;i++){
        let comp = ''
        let index = i
        let stack = [s.slice(0,i)]
        const add = (last) => {
            if(stack.length === 1) comp += last
            else comp += `${stack.length}${last}`
            stack = []
        }
        while(stack.length){
            const last = stack.at(-1)
            if(index > s.length){
                add(last)
                break
            }
            const next = s.slice(index, index+i)
            if(last && last !== next) add(last)
            stack.push(next)
            index += i
        }
        if(comp.length < answer) answer = comp.length
    }

    return answer
}
 ```
