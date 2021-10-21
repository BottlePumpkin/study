# Assert

assert 함수는 디버깅 모드에서만 동작합니다. 배포하는 애플리케이션에서는 제외됩니다. 주로 디버깅 중 조건의 검증을 위하여 사용합니다.

디버그 모드에서 특정한 코드라인에 에러가 발생 하게 되었을때 앱이 멈추게 되기 때문에 그 에러에 주의를 기울이게 됨.  물론, 테스트 코드를 작성하는 경우에 보통 사용 함!

> precondition(*:*:file:line:) 실제 배포 환경에서도 동작하는 함수.
> 

### Declaration

```swift
func assert(_ condition: @autoclosure () -> Bool,
 _ message: @autoclosure () -> String = String(),
 file: StaticString = #file,
 line: UInt = #line)

```

### Parameters

- condition

: 테스트 할 조건. (playgrond와 -Onone빌드에서만 평가 됨

- message

: condition으로 평가 되는 경우 인쇄할 문자열 

- file

: message Assert가 실패할 경우 안쇄할 파일 이름

- line

: message Assert가 실패할 경우 함께 인쇄할 줄 번호.

### Discussion

테스트 중에는 활성화 되지만 배송 코드 성능에 미치지 않는 내부 온전성 검사에 이 기능을 사용하십시오!

### Example

```swift
func tableView(_ tableView: UITableView,
               cellForRowAt indexPath: IndexPath) -> UITableViewCell {
    let anyCell = tableView.dequeueReusableCell(withIdentifier: "cell",
                                                for: indexPath)

    guard let cell = anyCell as? MyCustomCell else {
        assertionFailure("예상하지 못 한 셀 타입: \(type(of: anyCell))")
        return anyCell
    }

    // 셀 설정
    ...
}
```

공식 문서 

: [https://developer.apple.com/documentation/swift/1541112-assert](https://developer.apple.com/documentation/swift/1541112-assert)

참고 문서 

: [https://medium.com/@0xA1EC/asserts-in-swift-and-why-you-should-be-using-them-6a7c96eaec10#id_token=eyJhbGciOiJSUzI1NiIsImtpZCI6ImJiZDJhYzdjNGM1ZWI4YWRjOGVlZmZiYzhmNWEyZGQ2Y2Y3NTQ1ZTQiLCJ0eXAiOiJKV1QifQ.eyJpc3MiOiJodHRwczovL2FjY291bnRzLmdvb2dsZS5jb20iLCJuYmYiOjE2MzQ3ODIxNTAsImF1ZCI6IjIxNjI5NjAzNTgzNC1rMWs2cWUwNjBzMnRwMmEyamFtNGxqZGNtczAwc3R0Zy5hcHBzLmdvb2dsZXVzZXJjb250ZW50LmNvbSIsInN1YiI6IjEwMjY4NTYwMzU2NDQ4MzYzNzI3NiIsImVtYWlsIjoicDQ1Njl6ekBnbWFpbC5jb20iLCJlbWFpbF92ZXJpZmllZCI6dHJ1ZSwiYXpwIjoiMjE2Mjk2MDM1ODM0LWsxazZxZTA2MHMydHAyYTJqYW00bGpkY21zMDBzdHRnLmFwcHMuZ29vZ2xldXNlcmNvbnRlbnQuY29tIiwibmFtZSI6Iuuwleuzke2YuCIsInBpY3R1cmUiOiJodHRwczovL2xoMy5nb29nbGV1c2VyY29udGVudC5jb20vYS9BQVRYQUp5a3pJME9SalFXaEdCVGM1MUowdWpOOElSVE9FV1pMWFloV3d5MT1zOTYtYyIsImdpdmVuX25hbWUiOiLrs5HtmLgiLCJmYW1pbHlfbmFtZSI6IuuwlSIsImlhdCI6MTYzNDc4MjQ1MCwiZXhwIjoxNjM0Nzg2MDUwLCJqdGkiOiI2ZjUwMTA3ZTU4NGYyYzVkZWEwOTk2MjAwNDc0ZDlhOTYzN2U4YjU5In0.skbXXYz5xR8FIv-6oTDfiVmtkL_Rgo09DKhYAb7Brqjf9z2hjZUEROHI3SRMqQWN7e7ClrjZppj56XhJwzQ6Jkv2ocZakQzFVEEUlYKrPJmehEjuQJpqY7ggk2L4fSBRw3uXk_By72CnRm2jfPV2F5yhaKc-BjNxfPkys0YZitged0gMc-LfSMTiHZQs7ew3oryRoYXZJM_BMoW21IPzSgvHaqx-X5xutS1lex_QqJVd6HMX79Dq3nszk36JgyiiTB-gF2z6YXJkXDLMGTh7xfHXL1vtmS4-sN_M12bKeXWxUyMu7-Aq0_ahLc2ZZmEcL0F7EYdjTajJbWSMKp_qYg](https://medium.com/@0xA1EC/asserts-in-swift-and-why-you-should-be-using-them-6a7c96eaec10#id_token=eyJhbGciOiJSUzI1NiIsImtpZCI6ImJiZDJhYzdjNGM1ZWI4YWRjOGVlZmZiYzhmNWEyZGQ2Y2Y3NTQ1ZTQiLCJ0eXAiOiJKV1QifQ.eyJpc3MiOiJodHRwczovL2FjY291bnRzLmdvb2dsZS5jb20iLCJuYmYiOjE2MzQ3ODIxNTAsImF1ZCI6IjIxNjI5NjAzNTgzNC1rMWs2cWUwNjBzMnRwMmEyamFtNGxqZGNtczAwc3R0Zy5hcHBzLmdvb2dsZXVzZXJjb250ZW50LmNvbSIsInN1YiI6IjEwMjY4NTYwMzU2NDQ4MzYzNzI3NiIsImVtYWlsIjoicDQ1Njl6ekBnbWFpbC5jb20iLCJlbWFpbF92ZXJpZmllZCI6dHJ1ZSwiYXpwIjoiMjE2Mjk2MDM1ODM0LWsxazZxZTA2MHMydHAyYTJqYW00bGpkY21zMDBzdHRnLmFwcHMuZ29vZ2xldXNlcmNvbnRlbnQuY29tIiwibmFtZSI6Iuuwleuzke2YuCIsInBpY3R1cmUiOiJodHRwczovL2xoMy5nb29nbGV1c2VyY29udGVudC5jb20vYS9BQVRYQUp5a3pJME9SalFXaEdCVGM1MUowdWpOOElSVE9FV1pMWFloV3d5MT1zOTYtYyIsImdpdmVuX25hbWUiOiLrs5HtmLgiLCJmYW1pbHlfbmFtZSI6IuuwlSIsImlhdCI6MTYzNDc4MjQ1MCwiZXhwIjoxNjM0Nzg2MDUwLCJqdGkiOiI2ZjUwMTA3ZTU4NGYyYzVkZWEwOTk2MjAwNDc0ZDlhOTYzN2U4YjU5In0.skbXXYz5xR8FIv-6oTDfiVmtkL_Rgo09DKhYAb7Brqjf9z2hjZUEROHI3SRMqQWN7e7ClrjZppj56XhJwzQ6Jkv2ocZakQzFVEEUlYKrPJmehEjuQJpqY7ggk2L4fSBRw3uXk_By72CnRm2jfPV2F5yhaKc-BjNxfPkys0YZitged0gMc-LfSMTiHZQs7ew3oryRoYXZJM_BMoW21IPzSgvHaqx-X5xutS1lex_QqJVd6HMX79Dq3nszk36JgyiiTB-gF2z6YXJkXDLMGTh7xfHXL1vtmS4-sN_M12bKeXWxUyMu7-Aq0_ahLc2ZZmEcL0F7EYdjTajJbWSMKp_qYg)

,[https://pilgwon.github.io/blog/2017/09/25/Under-the-Hood-of-Assertions-in-Swift.html](https://pilgwon.github.io/blog/2017/09/25/Under-the-Hood-of-Assertions-in-Swift.html)

,[https://blog.yagom.net/561/](https://blog.yagom.net/561/)