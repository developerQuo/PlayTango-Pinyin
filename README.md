# PlayTango-Pinyin
## 탱고 병음학습 저작도구

### 개요
* 구분: 응용프로그램
* 제작인원: 1명(본인)
* 제작기간: 2019.09.20 ~ 2019.10.11 (약 3주)
* 주제: 중국어 병음의 교육 컨텐츠를 쉽고 빠르게 제작할 수 있는 저작도구.
* 용도: 컨텐츠 제작을 위한 업무지원용 프로그램으로 놀이판과 자유놀이를 제작하고 낱말카드에서 이들을 불러내어 문제와 정답을 제작할 수 있다.
* 특이사항
	+ 개발환경: python 3.7, Pycharm 2019.2, python virtualenv
	+ 라이브러리: PyQt5, pickle

### 메인 화면
***
<p align="center">
<img src="/img/메인.JPG" width="30%" height="20%" title="메인"></img>
</p>   
   
* 프로그램을 실행하면 메인 창이 뜬다.
* 버튼은 놀이판, 낱말카드가 있다.
	+ 놀이판에서는 screen과 init, block 텍스트파일을 출력할 수 있고 스크린파일을 만들고 저장한다.
	+ 낱말카드에서는 question_mp3, answer, answer_mp3, 음원 텍스트파일을 출력할 수 있고 음원파일을 만들고 저장한다.

### 놀이판 기본 화면
***
<p align="center">
<img src="/img/놀이판기본.JPG" width="60%" height="40%" title="놀이판기본"></img>
</p>   
   
* 왼쪽 상단에서는 놀이판용 음원을 작성.
* 왼쪽 하단에서는 저장된 놀이판들을 불러올 수 있다.
* 가운데 부분은 타공위치를 matrix로 표현.
	+ 0은 타공되지 않음을 표현.
	+ 1은 타공되었음을 표현.
	+ 5는 블럭의 기준을 표현.   
	__블럭모양(3x2)이 일정하므로 블럭단위로 타공한다.__
* 오른쪽 상단에서는 작업중에 자유놀이정보로 타공된 것을 확인할 수 있다.
* 오른쪽 하단에서는 작업물을 텍스트 파일로 저장하거나 ui를 닫을 수 있다.

### 놀이판 정보입력 화면
***
<p align="center">
<img src="/img/놀이판정보입력.JPG" width="60%" height="40%" title="놀이판정보입력"></img>
</p>   

### 놀이판 자유놀이 기본 화면
***
<p align="center">
<img src="/img/자유놀이기본.JPG" width="60%" height="40%" title="자유놀이기본"></img>
</p>   

### 놀이판 자유놀이 정보입력 화면
***
<p align="center">
<img src="/img/자유놀이정보입력.JPG" width="60%" height="40%" title="자유놀이정보입력"></img>
</p>   
   
* 좌우로 나뉜다. 이때 파란색 텍스트는 버튼이다. ex) 블럭을 누르면 행으로 블럭이 추가된다.
	+ 왼쪽은 블럭당 인식되는 좌표를 선택한다.
		- 앞서 놀이판에서 타공된 블럭들이 상단에 리스팅된다.
		- 블럭들의 이름을 사용자가 설정할 수 있다.
		- 체크박스를 체크하면 합계에 바로바로 집계된다.
		- 전체삭제도 가능하고 특정 블럭만 삭제도 가능하다.
	+ 오른쪽은 인식되는 좌표마다 음원을 삽입할 수 있다.
		- 블럭순서와 타공순서대로 리스팅된다.
		- 음원은 경로를 삽입하면 인식이되고 ','(쉼표)를 기준으로 음원 숫자를 집계한다.
		- 가장 오른쪽 숫자는 음원파일의 개수다.

### 놀이판 출력된 텍스트파일 (보드)
***
<p align="center">
<img src="/img/screen.JPG" width="60%" height="40%" title="놀이판보드텍스트파일"></img>
</p>   
   
* 타공된 위치를 0과 1로 표현하여 텍스트파일로 저장. __(5도 1로 표현)__
* 위의 형식으로 하드웨어가 텍스트파일을 읽는다.

### 놀이판 출력된 텍스트파일 (음원)
***
<p align="center">
<img src="/img/init.JPG" width="60%" height="40%" title="놀이판음원텍스트파일"></img>
</p>   
   
* 위의 형식으로 하드웨어가 텍스트파일을 읽는다.

### 놀이판 출력된 텍스트파일 (자유놀이)
***
<p align="center">
<img src="/img/block.JPG" width="60%" height="40%" title="놀이판자유놀이텍스트파일"></img>
</p>   
   
* 위의 형식으로 하드웨어가 텍스트파일을 읽는다.

### 낱말카드 문제탭 기본 화면
***
<p align="center"> 
<img src="/img/낱말카드기본.JPG" width="60%" height="40%" title="낱말카드문제탭기본화면"></img>
</p>   
   
* 낱말카드의 기본 화면.
* 상단의 빨간색과 파란색 텍스트는 버튼이다.
	+ 텍스트출력은 기본 음원과 문제 음원, 정답, 정답 음원을 출력.
	+ 문제 정답 정보를 클릭하면 저장된 놀이판을 선택하여 팝업을 띄운다.
* 왼쪽에서는 음원파일을 생성, 저장, 삭제할 수 있다. 
* 가운데 박스에서는 저장된 문제들을 불러올 수 있다.
* 설정에서는 기본 음원 정보를 작성할 수 있다.

### 낱말카드 정보입력 화면
***
<p align="center"> 
<img src="/img/낱말카드정보입력.JPG" width="60%" height="40%" title="낱말카드정보입력"></img>
</p>

### 낱말카드 문제정답 선택 화면
***
<p align="center"> 
<img src="/img/낱말카드_문제정답선택.JPG" width="60%" height="40%" title="낱말카드문제정답선택"></img>
</p>   
   
* 스크린을 선택하면 놀이판에 타공된 블럭 위치들과 블럭 개수가 뜬다.
* 확인을 누르면 문제정답정보로 이동하고 취소를 누르면 되돌아간다.

### 낱말카드 문제정답 정보 화면
***
<p align="center"> 
<img src="/img/낱말카드_문제정답정보.JPG" width="60%" height="40%" title="낱말카드문제정답정보"></img>
</p>   
   
* 좌우로 크게 둘로 나눈다.
	+ 왼쪽에서는 체크박스를 통해 해당 블럭에 문제와 정답을 설정할 것인지 체크.
	+ 오른쪽에서는 문제와 정답에 재생될 음원을 추가한다.
* 합계는 초록색 텍스트로 표현하고 하늘색 텍스트에는 버튼기능이 있다.
* ui를 닫으면 자동 저장된다.

### 기본 음원 텍스트파일 출력
***
<p align="center"> 
<img src="/img/mp3.JPG" width="60%" height="40%" title="기본음원텍스트파일"></img>
</p>   
   
* 위의 형식으로 하드웨어가 텍스트파일을 읽는다.

### 문제 음원 텍스트파일 출력
***
<p align="center"> 
<img src="/img/qMp3.JPG" width="60%" height="40%" title="문제음원텍스트파일"></img>
</p>   
   
* 위의 형식으로 하드웨어가 텍스트파일을 읽는다.

### 정답 텍스트파일 출력
***
<p align="center"> 
<img src="/img/answer.JPG" width="60%" height="40%" title="정답텍스트파일"></img>
</p>   
   
* 위의 형식으로 하드웨어가 텍스트파일을 읽는다.

### 정답 음원 텍스트파일 출력
***
<p align="center"> 
<img src="/img/aMp3.JPG" width="60%" height="40%" title="정답음원텍스트파일"></img>
</p>   
   
* 위의 형식으로 하드웨어가 텍스트파일을 읽는다.
