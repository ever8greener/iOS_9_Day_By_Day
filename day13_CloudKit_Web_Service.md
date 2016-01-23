.
# iOS 9 Day by Day
# 13. CloudKit Web Services

CloudKit JS 는 WWDC 15에 소개되었고, 이는 개발자들이 web interface를 이용하여 user들은 기존 CloudKit app의 것과 동일한 Container를 사용할 수 있게끔하는 것이다. CloudKit의 주된 제약중에 하나는 iOS와 OS X 에서만 사용가능했던(access) 것이다.  이 제약점을 이번에 제거함으로써 더욱더 많은 App 개발자들이 CloudKit을 사용하기를 바란다.

이번 포스트에서는, CloudKit JS 의 기능을 볼 것이며 샘플 노트 App을 만들 것이다. App을 사용해서 user들은 중요한 노트들을 cloud에 저장하게 해 줄 것이다. 

## CloudKit JS

CloudKit JS 는 아래 브라우저들을 지원한다:

- Safari
- Firefox
- Chrome
- IE
- Edge

흥미롭게도, node역시 지원하는데 이는 여러분의 자체 middle tier 서버로부터의 request를 실행하고 이를 여러분의 API로 포워드 할 수 있게 해 준다.

### CloudKit JS Application 만들기

CloudKit JS의 기능을 보여줄 데모앱을 사용하면 공유노트(shared notes)를 CloudKit에 저장할수 있다.

![완성된 첫 web application](images/CloudNotes.png)

자 이제 어떻게 이 app이 만들어 졌는지 하나씩 보자. CloudKit앱을 만들때 첫 걸음은 iCloud developer dashboard를 open하는 것이다(iOS 나 JS나 동일). 이 과정을 통해서 여러분들은 앱의 상세사항을 변경할 수 있고, record type설정, security roles설정, 데이터입력, 또 기타등등을 할 수 있다. 참고내용[https://icloud.developer.apple.com/dashboard](https://icloud.developer.apple.com/dashboard).

새App의 이름은 CloudNotes이다. 우선 모든세팅은 default로 두자.

App이 Setup 된 후, 새로운 record type를 지정해야 한다. 이 App은 제목과 내용을 포함한 간단한 note를 저장한다. 좌측의 'Schema' 아래 'Record Types'옵션을 선택하자. 'Users'record type은 이미 존재해 있을 것이다. 이는 기본적으로 생성된다.

add를 클릭하고 'CloudNote'라는 이름으로 new record type 를 생성하자. 이 레코드를 사용해서 데이터를 저장할 예정이다.

![Creating a CloudNote record type](images/cloudNote.png)
