## 📌 한림대학교 종합설계 프로젝트 [시스템 프로그래밍]
## 📕 Subject
* RasberryPi 4 Cluster, Tesseract, OpenCV, 네이버 맞춤법 검사기를 이용하여 사진속의 텍스트를 디지털 텍스트로 변환후 맞춤법 검사
## ⚙ Developer
* 조명근 : 영상처리, Tesseract, 웹 개발
* 이용하 : 클러스터 구성 및 맞춤법 검사
* 노영진 : 아날로그데이터 수집 및 영상처리
## ⚙ 개발 환경 및 사용한 오픈소스
* Raspberry 4
* Raspbian buster
* Apache
* Python 3.7
* [Tesseract 4](https://github.com/tesseract-ocr/tesseract)
* [OpenCV 4.1.2](https://github.com/opencv)
* [MPICH 3.2](https://mpich.org)
* 네이버 맞춤법 검사기
## 📒 Project Info
1.  사진 속의 텍스트를 디지털 텍스트로 변환한 뒤에 인식률을 높이기 위해서 OpenCV를 사용해 이미지를 전처리
    1.  이미지 회색조로 변경
    2.  크기를 정형화 시킴(resize)
    3.  가우시안 필터 적용
    4.  이미지 이진화
2.  전처리한 이미지를 Tesseract를 사용해 디지털 텍스트로 변환
3.  마지막으로, 네이버 맞춤법 검사기를 사용해 맞춤법 검사
    1.  네이버 맞춤법 검사기의 `검사하기` 버튼을 눌렀을때 요청하는 URL 주소를 추출 및 어떤 Parameter를 보내는지 분석(크롬 개발자 모드 활용)
    2.  형식에 맞게 request를 보내고 response를 받음.
    3.  [맞춤법 검사 코드](https://github.com/dding-g/Tesseract_Korean_Converter/blob/master/OCR/han_spell.py)
4.  클러스터는 전반적인 연산을 담당하며, 낮은 가격에 최대한의 효율을 도출해 내기 위해 구성하였음. 
## 🥕 Project Result
* 라즈베리파이4 클러스터
    * ![image](https://user-images.githubusercontent.com/29707967/82061388-9ba1f500-9703-11ea-8261-2313ab5a4619.png)
* 프로젝트 다이어그램
    * ![image](https://user-images.githubusercontent.com/50908416/70037432-e5859b80-15f9-11ea-9389-5ce549cb98a3.png)
* 원본 파일
    * ![원본](https://user-images.githubusercontent.com/50908416/69917893-6df72580-14ae-11ea-84a7-58eed32f9519.jpg)
* 전처리 후 파일
    * ![전처리](https://user-images.githubusercontent.com/50908416/69917894-6e8fbc00-14ae-11ea-8643-b1f7602b5f32.PNG)
* 결과물
    * ![image](https://user-images.githubusercontent.com/50908416/69995253-18487900-1593-11ea-8fcb-c7a11816d51c.png)

## 프로젝트 사용 방법
* compile
`cc -o parell_task.o -I/usr/include/python2.7 parell_task.c -lpython2.7`
* run
`mpirun -np 4 -f machinefile ./parell_task.o`
* ![image](https://user-images.githubusercontent.com/50908416/70001141-dd990d80-159f-11ea-97dd-01ce61341e2f.png)
## 프로젝트 필요성 및 활용방안
* 대량의 아날로그 텍스트를 디지털 텍스트로 변환할 때 간편하게 사용할 수 있습니다.
* 한글로 작성된 고서 같은 오래된 문서들을 디지털 파일로 변환하고, 
* 한글 맞춤법 검사를 통해 텍스트를 정확하게 변환하는 효과를 기대할 수 있습니다.
* 맞춤법을 제대로 사용하지 못하는 요즘 시대의 학생들이 좀 더 정확한 문법으로 작성할 수 있게 도와줄 수 있을 것으로 생각됩니다.

## 🏅 캡스톤 발표 결과 : 은상
