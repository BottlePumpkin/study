# URL

## URL 타입

인코딩되지 않은 주소를 URL의 형태로 관리 합니다.

```swift
let urlString = "https://itunes.apple.com/search?media=music&entity=musicVideo&term=collier"
let url = URL(string: urlString)
```

URL의 stirng은 영문,숫자와 특정 문자만 인식 가능하며,

한글 띄어쓰기 등은 인식하지 못합니다.

아래 메소드를 통해 URL로 몇몇 정보를 가져 올 수 있습니다.

```swift
url?.absoluteString // 절대주소 (urlString과 동일)
url?.scheme // http? htttps?
url?.host // "itunes.apple.com"
url?.path // "/search"
url?.query // "media=music&entity=musicVideo&term=collier"
```

## URL - relativeTo:

상대 주소를 추가 할 때 사용합니다.

```swift
let baseURL = URL(string: "https://itunes.apple.com")
let relativeURL = URL(string: "search", relativeTo: baseURL)
relativeURL?.absoluteString // "https://itunes.apple.com/search"
relativeURL?.baseURL // https://itunes.apple.com (URL? 타입)
relativeURL?.path // "/search"
```

### URLComponents 타입

URL에 포함되어 있는 한글, 띄어쓰기 등을 자동으로 인코딩 하여 관리합니다. 쿼리 파라미터 등은 URLQueryItem 타입의 변수를 하여 별도로 관리합니다.

```swift
var urlComponents = URLComponents(string: "https://itunes.apple.com/search?")!
let mediaQuery = URLQueryItem(name: "media", value: "music")
let entityQuery = URLQueryItem(name: "entity", value: "song")
let termQuery = URLQueryItem(name: "term", value: "jacob collier")
urlComponents.queryItems?.append(mediaQuery)
urlComponents.queryItems?.append(entityQuery)
urlComponents.queryItems?.append(termQuery)

urlComponents.url?.scheme // "https"
urlComponents.string 
// "https://itunes.apple.com/search?media=music&entity=song&term=jacob%20collier"
urlComponents.queryItems // 밑에
```

참조 문서 : [http://yoonbumtae.com/?p=3499](http://yoonbumtae.com/?p=3499)