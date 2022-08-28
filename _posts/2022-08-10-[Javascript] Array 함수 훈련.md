---
layout: post
title: [Javascript] Array 함수 훈련
date: 2022-08-10 23:18 +0900
tags: [javascript]
---

### [Javascript] Array 함수 훈련

---

교육을 받으며 array 함수의 중요성을 다시금 깨닫게 되었다

실무나 알고리즘 테스트 등에서도 굉장히 많이 쓰이니 뼛속까지 깊숙히 스며들도록 

반복된 훈련을 통해 익히도록 하자

아래는 훈련시 문제와 사용한 함수이다

실제로는 더 복잡하게 사용되지만 일단 어떤 함수들이 있으며 ,

어떻게 사용되는지 간단 명료하게 정리하였다.

```javascript
// Q1. make a string out of an array
{
  const fruits = ["apple", "banana", "orange"];
  const join = fruits.join(",");
  console.log(join);
}

// Q2. make an array out of a string
{
  const fruits = "🍎, 🥝, 🍌, 🍒";
  const result = fruits.split(",");
  console.log(result);
}

// Q3. make this array look like this: [5, 4, 3, 2, 1]
{
  const array = [1, 2, 3, 4, 5];
  const result = array.reverse();
  console.log(result);
  console.log(array);
}

// Q4. make new array without the first two elements
{
  const array = [1, 2, 3, 4, 5];
  const result = array.splice(1, 3); // 1번째 인덱스부터 시작하여 3개의 요소 추출 - 기존배열 수정
  console.log(result);
  console.log(array);
}
{
  const array = [1, 2, 3, 4, 5];
  const result = array.slice(1, 3); //  1번째 인덱스부터 3번째 인덱스를 제외한 2번째 인덱스까지 - 기존배열 유지
  console.log(result);
  console.log(array); // 기존배열 유지
}

class Student {
  constructor(name, age, enrolled, score) {
    this.name = name;
    this.age = age;
    this.enrolled = enrolled;
    this.score = score;
  }
}
const students = [
  new Student("A", 29, true, 45),
  new Student("B", 28, false, 80),
  new Student("C", 30, true, 90),
  new Student("D", 40, false, 66),
  new Student("E", 18, true, 88),
];

// Q5. find a student with the score 90
{
  const result = students.find((students) => students.score === 90);
  console.log(result);
}

// Q6. make an array of enrolled students
{
  const result = students.filter((students) => students.enrolled);
  console.log(result);
}

// Q7. make an array containing only the students' scores
// result should be: [45, 80, 90, 66, 88]
{
  const result = students.map((students) => students.score);
  console.log(result);
}
{
  const result = students.map((students) => students.score * 2);
  console.log(result);
}

// Q8. check if there is a student with the score lower than 50
{
  const result = students.some((students) => students.score < 50); // 배열요소 중 하나라도 조건에 만족하면 true 반환
  console.log(result);
}
{
  const result = students.every((students) => students.score < 50); // 배열요소 모두 조건에 만족하면 ture 반환 // 하나라도 만족못하면 false 반환
  console.log(result);
}

// Q9. compute students' average score
{
  const result = students.reduce((prev, curr) => prev + curr.score, 0); // reduce 원하는 시작점부터 배열을 돌며 값을 누적한다
  console.log(result / students.length);
}

// Q10. make a string containing all the scores
// result should be: '45, 80, 90, 66, 88'
{
  const result = students
    .map((students) => students.score)
    .filter((score) => score >= 50)
    .join();
  console.log(result);
}

// Bonus! do Q10 sorted in ascending order
// result should be: '45, 66, 80, 88, 90'
{
  const result = students
    .map((students) => students.score)
    .sort((a, b) => a - b)
    .join();
  console.log(result);
}
```
