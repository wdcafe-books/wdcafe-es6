
# CH12. ES6 JSON

<br>
<br>

## 1. JSON 소개

JSON(JavaScript Object Notation)은 데이터를 효율적으로 저장하고 교환하기 위해 사용되는 경량의 데이터 형식입니다. 

주로 웹에서 데이터를 전송하거나 저장하는 데 많이 사용되며, 현재 거의 모든 프로그래밍 언어에서 지원합니다. JSON은 사람과 기계가 모두 이해하기 쉬운 텍스트 기반의 데이터 형식입니다.

<br>  

### 1) JSON의 특징

1. **간결하고 가독성이 좋음**: JSON은 텍스트 기반이기 때문에 사람이 읽고 쓰기 쉽습니다. 객체와 배열의 중첩 구조로 데이터를 표현할 수 있어 복잡한 데이터도 표현할 수 있습니다.
2. **독립적인 데이터 형식**: JSON은 언어나 플랫폼에 독립적입니다. 따라서 자바스크립트 뿐만 아니라 다양한 프로그래밍 언어에서 JSON을 사용할 수 있습니다.
3. **간단한 데이터 구조**: 주로 객체와 배열을 기반으로 하며, 키-값 쌍으로 데이터를 표현합니다. 이러한 구조는 다양한 데이터를 쉽게 표현하고 다룰 수 있게 합니다.
4. **효율적인 데이터 교환**: 네트워크를 통해 데이터를 전송할 때 JSON을 사용하면 데이터 크기를 작게 유지하면서도 데이터를 효율적으로 교환할 수 있습니다.

<br>  

### 2) JSON의 구조 예시

JSON은 객체와 배열을 중심으로 구성됩니다. 예를 들어, 다음과 같은 JSON 데이터가 있습니다:
 

```
{
  "name": "Alice",
  "age": 30,
  "city": "New York",
  "skills": ["JavaScript", "Python", "React"],
  "address": {
    "street": "123 Main St",
    "zip": "10001"
  }
}
```

<br>

이 데이터는 이름, 나이, 도시, 기술 목록, 주소 등을 포함하고 있습니다. 객체 안에 또 다른 객체나 배열이 중첩되어 있는 구조입니다.

<br>

  

### 3) JSON의 사용 예시


#### A. 데이터 전송

웹 애플리케이션에서 서버로부터 JSON 형식의 데이터를 받아와서 화면에 표시하는 경우가 많습니다. 이를 통해 데이터를 효율적으로 전송하고 사용할 수 있습니다.

<br>

#### B. 설정 파일

웹 애플리케이션의 설정이나 구성 정보를 JSON 파일로 저장하여 사용할 수 있습니다. 예를 들어, 서버 주소, 데이터베이스 설정 등을 JSON 파일로 관리할 수 있습니다.

<br>

#### C. API 통신

대부분의 웹 API는 JSON 형식으로 데이터를 주고받습니다. 클라이언트에서 서버로 데이터를 전송할 때도 JSON을 사용하여 구조화된 데이터를 송수신할 수 있습니다.

<br>  

### 4) JSON의 제한 사항

- JSON은 데이터의 형태를 정의하고 있기 때문에 함수나 메서드 정의, 원시 자료형을 직접 표현할 수 없습니다.
- JSON 데이터는 반드시 문자열 형태로 전달되어야 하며, JavaScript에서는 `JSON.parse()`와 `JSON.stringify()` 메서드를 사용하여 객체와 문자열 간의 변환을 수행할 수 있습니다.

<br>
<br>   

## 2. 예시 샘플

<br>

- HTML

```
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>ES6 - JSON 문법</title>
</head>
<body>
   
  <h1>24. ES6 - JSON 문법</h1>

  <p>JSON(JavaScript Object Notation)은 데이터를 효율적으로 표현하고 전송하기 위한 경량의 데이터 형식입니다. JSON은 텍스트 형식이며, JavaScript 객체를 기반으로 하고 있어 JavaScript에서 쉽게 파싱하고 생성할 수 있습니다. 또한 다른 프로그래밍 언어에서도 널리 사용되고 있습니다.</p>

  <h2>JSON의 특징</h2>

  <ol>
    <li>가독성: 사람이 읽고 쓰기에 용이한 텍스트 형식으로 데이터를 표현합니다.</li>
    <li>간결성: 중첩된 구조로 데이터를 표현하여 복잡한 데이터도 표현할 수 있습니다.</li>
    <li>상호 운용성: 다양한 프로그래밍 언어에서 지원하고 있어 서로 다른 시스템 간에 데이터를 주고받기에 적합합니다.</li>
  </ol>

  <h2>컴퓨터 프로그래밍 언어에서 데이터를 서버에서 수신할 때 사용되는 형식 3가지</h2>

  <h3>1) CSV(Comma Separated Values) 형식</h3>
  <ul>
    <li>각 항목을 쉼표로 구분해서 데이터 표현</li>
    <li>장점 : 용량이 적고, 간단해 보임</li>
    <li>단점 : 각 데이턱가 무엇을 의미하는지 알기 어려움</li>
    <li></li>
  </ul>
  <p>
    <pre style="background-color: #ccc; color:#222">
      <code>
        ex. value1, value2, value3, ...
      </code>       
    </pre>   
  </p>

  <h3>2) XML 형식</h3>
  <ul>
    <li>각 항목을 쉼표로 구분해서 데이터 표현</li>
    <li>대부분의 정보 사이트에서 RSS로 데이터를 제공할 때 사용합니다.</li>
    <li>장점 : 데이터가 어떤 것을 의미하는지 알 수 있습니다.</li>
    <li>단점 : 여는 태그와 닫는 태그로 이루어져 쓸데없는 용량을 많이 차지합니다.</li>
  </ul>
  <p>         
    <pre style="background-color: #ccc; color:#222">
      <code>
        <?xml version="1.0" encoding="UTF-8"?>
        <friend>
          <name>Charlie</name>     
          <name>Steve</name>     
        </friend>
      </code>       
    </pre>   
  </p>

  <h3>3)JSON 형식</h3>
  <ul>
    <li>텍스트 형식이며, JavaScript 객체를 기반으로 한 데이터를 효율적으로 표현하고 전송하기 위한 경량의 데이터 형식입니다.</li>
    <li>데이터를 이름/값 쌍으로 이루어져 있어야 합니다.</li>
    <li>데이터는 쉼표로 구분하고, 중괄호는 객체, 대괄호는 배열을 포함합니다.</li>
    <li>장점 : JS객체와 비슷해 문법 습득이 쉽습니다.</li>
    <li>단점 : 키명을 다 적어야 하므로 데이터의 양이 엄청나게 많아지면 데이터 추출 속도가 느립니다.</li>
  </ul>

  <p>
    <pre style="background-color: #ccc; color:#222">
      <code>
        { "key1": value1, "key2": value2 }   <= JS와 다르게 Key에 큰따옴표를 붙임!
        {
          "name": "John",
          "age": 30,
          "city": "New York",
          "hobbies": ["reading", "traveling", "photography"],
          "address": {
            "street": "123 Main St",
            "zip": "10001"
          }
        }
      </code>       
    </pre>  
  </p>

  <h3>4) JSON 데이터 유형 : JSON 키의 값의 유형은 아래 6가지입니다.</h3>
  <p>ex. 문자열, 숫자, 객체, 배열, true/false, null</p>
  <p>
    <pre style="background-color: #ccc; color:#222">
      <code>        
        [
          {
            "group": "방탄소년단",
            "debut": 2013,
            "email": true,
            "members": "진", "RM", "슈가", "제이콥", "지민", "뷔", "정국",
            "member1": {
              "name":"진",
              "age":31,
              "hobby": null
            }
          }
        ]
      </code>       
    </pre>  
  </p>

  <script>

    /* 샘플 주소
      엑셀데이터 샘플 : https://docs.google.com/spreadsheets/d/1-BMfuw9nuP0ZtXGSmg_BJCsP9RXV26RBhIVLHAiDQ8Y/edit#gid=0
      엑셀 to JSON 변환사이트 :  https://shancarter.github.io/mr-data-converter/         
    */

    // JavaScript 객체를 JSON 문자열로 변환 :   
    // -  웹에서 데이터를 수신할 때 데이터는 항상 문자열입니다. 자바스크립트가 데이터를 다시 분석하려면  객체데이터로 변경해야 합니다. 


    //  1) JSON.parse() :  JSON 형식의 문자열을 JavaScript 객체로 변환합니다.
    // - 주로 서버에서 받은 JSON 데이터를 JavaScript에서 사용하기 위해 객체로 변환할 때 사용됩니다.
    const jsonString = '{"name": "John", "age": 30}';     // JSON Data 
    const data = JSON.parse(jsonString);                  // 객체로 변환
    console.log(typeof data);                             //  Object
    console.log(data.name);                               // "John" 출력                 <= 객체 Data 출력
    
    //  2) JSON.stringify() :  JavaScript 객체를 JSON 형식의 문자열로 변환합니다.
    // - 주로 자바스크립트 객체를 서버로 전송하기 위해 JSON 형식으로 변환할 때 사용됩니다.
    const user = { name: "Alice", age: 25 };              // 객체 Data
    const json = JSON.stringify(user);                    // JSON으로 변환
    console.log(typeof json);                             //  String  <= JSON 형식의 문자열
    console.log(json);                                    // '{"name":"Alice","age":25}' <= JSON Data 


  </script>

</body>
</html>
```