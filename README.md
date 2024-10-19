# javascript-calculator-precourse


## 기능 명세
### 시작, 마무리 세팅
- [ ] 실행시 console API로 안내문과 입력을 받도록 하는 함수 구현
- [ ] 시작 숫자는 `let result = 0;`으로 시작하기
- [ ] 출력 함수 구현 `결과 : ${result}` (console API 사용)

### 숫자 연산 시작 전에 커스텀 구분자 확인 함수
- [ ] 반복문으로 체크 (커스텀 구분자가 여러 개 있을 수 있음)
- [ ] `//`과 `\n` 를 체크하고 그 사이의 문자열을 변수에 담아넣음
- [ ] `[Error]` 처리
	- [ ] 커스텀 구분자의 '문자열'이 존재하지 않는 경우
	- [ ] 커스텀 구분자의 문자열이 쉼표`,`나 콜론`:`이면 `[Error]` 반환
	- [ ] 커스텀 구분자가 숫자로 시작한다면 `[Error]` 반환
	- [ ] 음수를 더해야하는 경우도 있기에 구분자가 마이너스`-`라면 `[Error]` 반환
- [ ] 구분자 체크가 끝난다면 입력한 문자열에서 구분자 전달 부분까지 문자열 위치 확인
- [ ] 구분자끼리 겹친다면 **먼저 나온 문자열** 우선

### 숫자 더하기 함수는 문자열 순회를 돌면서 확인 (while 문)
- [ ] 순회 하는 동안 지금 위치가 구분자인지 확인하는 함수
	- [ ] 쉼표와 콜론을 먼저, 그 다음 커스텀 문자열 순
	- [ ] 커스텀 문자열인지 확인하는 중에 만약 순회가 끝난다면 `[Error]` 출력 (커스텀 문자열인줄 알았지만 아니라는 의미 -> 다른 문자열)
- [ ] 처음부터 순회를 돌면서 **구분자가 나오기 전**까지 문자열 하나 만들기
	- [ ] 지금 문자열 위치가 구분자인지 아닌지 확인하는 함수 실행
	- [ ] 구분자가 아니라면 문자열에 계속 해당 위치의 문자를 더함
	- [ ] 구분자가 나오거나 문자열 순회가 끝나면 number 타입으로 변환
	- [ ] `[Error]` 처리
		- [ ] number 타입 변환 실패시 `[Error]` 반환
		- [ ] 계산기인데, 계산을 1번도 하지 않는다면 `[Error]` 반환
