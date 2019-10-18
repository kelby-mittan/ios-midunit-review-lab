## Mid Unit-1 Review


## Strings

1. **Given a String, return a String with each letter uppercased**

Input: `Hello, there`

Output: `HELLO, THERE`

# Answer
```swift
var helloThere = "Hello, there"
helloThere = helloThere.uppercased()
```

2. **Given a String, return a String alternating between uppercase and lowercase letters**


Input: `Hello, there`

Output: `HeLlO, tHeRe`


3. **Given a String, return a String with all occurrences of a given letter removed**

Input: `Hello, there`

Output: `Hllo, thr`


## Arrays


1. **Given an array of type [Int], return the largest element**

Input: `[1,5,2,4,1,4]`

Output: `5`

# Answer
```swift
var largestInArray = [1, 5, 2, 4, 1, 4]
var largestNum = largestInArray[0]
for num in largestInArray {
    if num >= largestNum {
        largestNum = num
    }
}
print(largestNum)
```

2. **Given an array of type [Int], return the smallest element**

Input: `[1,5,2,4,1,4]`

Output: `1`
# Answer
```swift
var smallestInArr = [1, 5, 2, 4, 1, 4]
var smallestNum = smallestInArr[0]
for num in smallestInArr {
    if num <= smallestNum {
        smallestNum = num
    }
}
```
3. **Given an array of type [Int], return its sum**

Input: `[1,5,2,4,1,4]`

Output: `17`
# Answer 
```swift
var sumArr = [1, 5, 2, 4, 1, 4]
var sum = 0
for num in sumArr {
    sum += num
}
print(sum)
```
4. **Given an array of type [Double], return its average**

Input: `[3,4.5,7.5,2,1]`

Output: `3.6`
```swift
var doubleArr: [Double] = [3,4.5,7.5,2,1]
var doubleSum: Double = 0
var doubleCount = Double(doubleArr.count)
for num in doubleArr {
    doubleSum += num
}
let doubleAvg = doubleSum / doubleCount
print(doubleAvg)
```
5. **Given an array of type [Double] and a Double, return the sum of all numbers in the array greater than a given number**

Input: `[3,4.5,7.5,2,1], 3`

Output: `12`

```swift
var doubleArray: [Double] = [3,4.5,7.5,2,1]
var doubleSum2: Double = 0
for num in doubleArray where num > 3 {
    doubleSum2 += num
}
```

6. **Given an array of type [Double], return the product of all the elements**

Input: `[3,4.5,7.5,2,1]`

Output: `202.5`
```swift
var doubleArray3: [Double] = [3,4.5,7.5,2,1]
var doubleProduct: Double = 1
for num in doubleArray3 {
    doubleProduct *= num
}
```

7. **Given an array of type [Int], return the second smallest value in the array**

Input: `[3,6,1,9,4,8]`

Output: `3`
# Answer
```swift
var smallestInArray2 = [3,6,1,9,4,8]
var smallestNum2 = smallestInArray2[0]
for num in smallestInArray2 {
    if num <= smallestNum2 {
        smallestNum2 = num
    }
}

var secondSmallestNum = smallestInArray2[0]
for num in smallestInArray2 where num > smallestNum2 {
    if num <= secondSmallestNum {
        secondSmallestNum = num
    }
}
```

## Optionals

1. **Given an array of type [String?] return an array of [String] removing all nil values**

Input: `[nil, "We", "come", nil, "in", "peace"]`

Output: `["We", "come", "in", "peace"]`
# Answer
```swift
var stringArray = [nil, "We", "come", nil, "in", "peace"]
var nonNilArray = [String]()
for string in stringArray {
    if let validString = string {
        nonNilArray.append(validString)
    }
}
print(nonNilArray)
```
2. **Given an array of type [String?]? return an array of [String] removing all nil values**

Input: `nil`

Output: `[]`
# Answer
```swift
var nilArray = [String?]()
var removedNil = [String]()
for string in nilArray {
    if let validString = string {
        removedNil.append(validString)
    }
}
```
3. **Given an array of type [Int?] return the sum of all non-nil values.  Use guard statements in your solution.**

Input: `[4, nil, 9, 5, nil]`

Output: `18`
# Answer
```swift
var intArr = [4, nil, 9, 5, nil]
var intSum = 0
for num in intArr {
    guard let num = num else {
        continue
    }
    intSum += num
}
```
4. **Given an array of type [Int?]? return the sum of all non-nil values.  Use guard statements in your solution.**

Input: `nil`

Output: `0`

5. **Given an array of type [Int?] and an optional Int, return the sum of all values not equal to the given number.  If the given number is nil, return the sum of all non-nil values.**

Input: `[1, 1, nil, 3, 5, nil, 1, nil, 3, 5, nil, 5, nil, 3], 1`

Output: `24`
# Answer
```swift
var intArr2 = [1, 1, nil, 3, 5, nil, 1, nil, 3, 5, nil, 5, nil, 3]
var intSum2 = 0
for num in intArr2 {
    if let validNum = num {
        if validNum != 1 {
            intSum2 += validNum
        }
    }
}
```

## Dictionaries

1. **Given an array of type [String], return a copy of the array with all duplicate values removed**

Input: `["apple", "apple", "banana", "banana", "banana", "cake", "cake"]`

Output: `["apple", "banana", "cake"]`
# Answer
```swift
var fruitArr = ["apple", "apple", "banana", "banana", "banana", "cake", "cake"]
var fruitSet = Set(fruitArr)
var fruitArrNoDuplicates = Array(fruitSet.sorted())
print(fruitArrNoDuplicates)
```
2. **Given a String, find the most frequently occurring letter**

Input: `Never trust a computer you can't throw out a window ~ Steve Wozniak`

Output: `t`
# Answer 
```swift
var wozQuote = "Never trust a computer you can't throw out a window ~ Steve Wozniak"
var wozLowercased = wozQuote.lowercased()
var countDict = [Character: Int]()
for letter in wozLowercased {
    if let countNum = countDict[letter] {
        countDict[letter] = countNum + 1
    } else {
        countDict[letter] = 1
    }
}
print(countDict)
var mostOccurences = 0
for (char, count) in countDict {
    if char != " " {
        if count >= mostOccurences {
            mostOccurences = count
        }
    }
}
print(mostOccurences)
var mostLetter: Character = " "

for (char, count) in countDict {
    if count == mostOccurences {
        mostLetter = char
    }
}
print(mostLetter)
```
3. **Given an array of type [Int], return a copy of the array that contains only elements that appear at least twice**

Input: `[1,1,2,3,3,3,4,5,6,6,7]`

Output: `[1,3,6]`
# Answer
```swift
var intergerArr = [1,1,2,3,3,3,4,5,6,6,7]
var intsOfTwoOrMore = [Int]()
func freqOfInt(arr: [Int]) -> [Int: Int] {
    var freqDict = [Int: Int]()
    for num in arr {
        if let count = freqDict[num] {
            freqDict[num] = count + 1
        } else {
            freqDict[num] = 1
        }
    }
    return freqDict
}

for element in freqOfInt(arr: intergerArr) {
    if element.value >= 2 {
        intsOfTwoOrMore.append(element.key)
    }
}
print(intsOfTwoOrMore.sorted())
```

4. **Given a String, find the second most frequently occurring letter in a string**

Input: `Never trust a computer you can't throw out a window ~ Steve Wozniak`

Output `o`

# Answer 
```swift
var wozQuote = "Never trust a computer you can't throw out a window ~ Steve Wozniak"
var wozLowercased = wozQuote.lowercased()
var countDict = [Character: Int]()
for letter in wozLowercased {
    if let countNum = countDict[letter] {
        countDict[letter] = countNum + 1
    } else {
        countDict[letter] = 1
    }
}
print(countDict)
var mostOccurences = 0
for (char, count) in countDict {
    if char != " " {
        if count >= mostOccurences {
            mostOccurences = count
        }
    }
}
print(mostOccurences)
var mostLetter: Character = " "

for (char, count) in countDict {
    if count == mostOccurences - 1 {
        mostLetter = char
    }
}
print(mostLetter)
```

## Closures

1. **Given an array of type [String], return an array that contains the Strings sorted alphabetically with capital letters first (Swift will do that part automatically)**

Input: `["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]`

Output: `["Never", "a", "a", "can\'t", "computer", "out", "throw", "trust", "window", "you"]`
# Answer
```swift
let strArr = ["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]
let sortedStrArr = strArr.sorted()
print(sortedStrArr)
```
2. **Given an array of type [String], return an array that contains the Strings sorted by length**

Input: `["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]`

Output: `["a", "a", "you", "out", "Never", "trust", "can\'t", "throw", "window", "computer"]`
# Answer
```swift
var sortedLengthArr = [String]()
let strArr2 = ["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]
sortedLengthArr = strArr2.sorted() { $0.count < $1.count }
print(sortedLengthArr)
```
3. **Given an array of type [String], return an array containing all Strings at least 4 characters long**

Input: `["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]`

Output: `["Never", "trust", "computer", "can\'t", "throw", "window"]`
# Answer
```swift
var sortedByFour = [String]()
let strArr3 = ["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]
for word in strArr3 {
    if word.count >= 4 {
        sortedByFour.append(word)
    }
}
print(sortedByFour)
```
4. **Given an array of type [String], return a String containing all of the Strings from the array combined and separated by spaces.  Do this first without using the `joined(separator:) method`**

Input: `["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]`

Output: `Never trust a computer you can't throw out a window`
# Answer
```swift
var strArr4 = ["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]
var arr4WithSpaces = [String]()
for word in strArr4 {
    arr4WithSpaces.append(word + " ")
}
print(arr4WithSpaces.joined())
```

## Enums


1. **Given an array of type [Int] and an instance of NumberType (defined below), return an array containing only all the even or odd numbers.**

```swift
enum NumberType {
    case even
    case odd
}
```

Input: `[1,2,3,4,5,6], NumberType.odd`

Output: `[1,3,5]`
# Answer
```swift
enum NumberType {
    case even
    case odd
}
func evenOrOdd(arr: [Int], eOrO: NumberType) -> [Int] {
    var outputArr = [Int]()
    for num in arr {
        switch eOrO {
        case .even:
            if num % 2 == 0 {
                outputArr.append(num)
            }
        case .odd:
            if num % 2 != 0 {
                outputArr.append(num)
            }
        }
    }
    return outputArr
}
print(evenOrOdd(arr: [1,2,3,4,5,6], eOrO: .odd))
```
2. **Given a String and an instance of StringType (defined below), return the String either lowercased or uppercased**

```swift
enum StringType {
    case lowercase
    case uppercase
}
```

Input: `"Design is not just what it looks like and feels like. Design is how it works", .uppercase`

Output: ``"DESIGN IS NOT JUST WHAT IT LOOKS LIKE AND FEELS LIKE. DESIGN IS HOW IT WORKS"``
# Answer
```swift
enum StringType {
    case lowercase
    case uppercase
}
func lowerOrUpper(takeIn: String, lowOrUp: StringType) -> String {
    var strAction = String()
    switch lowOrUp {
    case .lowercase:
        strAction = takeIn.lowercased()
    case .uppercase:
       strAction = takeIn.uppercased()
    }
    return strAction
}
print(lowerOrUpper(takeIn: "Design is not just what it looks like and feels like. Design is how it works", lowOrUp: .uppercase))
```
3. **Given an array of type [FileStatus] (defined below) and an Int, return an array containing only files that were saved more than that many times**

```swift
enum FileStatus: CustomStringConvertible {
    case unsaved
    case saved(numberOfVersions: Int)
    var description: String {
        switch self {
        case .unsaved: return "Unsaved File"
        case let .saved(numberOfVersions): return "File that has been saved \(numberOfVersions) times"
        }
    }
}
```

Input: `[FileStatus.saved(numberOfVersions: 5), FileStatus.saved(numberOfVersions: 3), FileStatus.saved(numberOfVersions: 8)], 4`

Output: `[File that has been saved 5 times, File that has been saved 8 times]`
