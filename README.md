# assignment_recursion_sprint_node

Again and again and again and again and again...

[A recursion assignment which uses Node for the Viking Code School](http://www.vikingcodeschool.com)

```
const factorialIterative = (num) => {
  let result = 1;
  for(let i = num; i >= 1; i--){
    result *= i
  }
  return result
}

const factorialRecursive = (num) => {
  //base case
  if(num == 1){return 1}

  num = num * factorialRecursive(num - 1)

  return num
}

sumdigIterative = (num) => {
  num = num.toString().split("")
  num = num.map((str) => {return parseInt(str)})

  const reducer = (accumulator, currentValue) => accumulator + currentValue;

  return num.reduce(reducer)
}

sumdigRecursive = (num) => {
  //base case
  if(num.toString().split("").length === 1){
    return num
    console.log(num)
  }

  let arr = num.toString().split("")

  let end = arr.pop()
  end = parseInt(end)

  let remaining = arr.join("")
  remaining = parseInt(remaining)

  return sumdigRecursive(end) + sumdigRecursive(remaining)
}

palindromeIterative = (string) => {

  let secondpointer = string.length - 1
  let arr = string.split("")

  let palindromeQuestion = true
  arr.forEach((char) => {
    if (char !== arr[secondpointer]) {
      palindromeQuestion = false
    }
      secondpointer -= 1
  })

  return palindromeQuestion
}

palindromeRecursive = (string, startidx = 0) => {
  //base case
  if(startidx > string.length / 2){
    return true
  }

  let palindromeQuestion = false
  if(string[startidx] === string[string.length - 1 - startidx]){
    palindromeQuestion = true
  }

  return palindromeQuestion && palindromeRecursive(string, startidx += 1)
}
```
