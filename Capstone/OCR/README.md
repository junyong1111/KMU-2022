OCR:  
광학 문자 인식(Optical character recognition; OCR)은 사람이 쓰거나 기계로 인쇄한 문자의 영상을 이미지 스캐너로 획득하여 기계가 읽을 수 있는 문자로 변환하는 것

- 테서랙트(Tesseract):     
  - 다양한 운영 체제를 위한 광학 문자 인식 엔진 이 소프트웨어는 Apache License, 버전 2.0 에 따라 배포되는 무료 소프트웨어이며 2006년부터 Google에서 개발을 후원

  - 2006년 테서랙트는 당시 가장 정확한 오픈 소스 OCR 엔진 중 하나로 간주되었다.

##### 한글인식이 상당히 좋지않은편이라 학습 또는 이미지 전처리 과정이 필요

- OCR.py 
  - 영수증인식 후 나온 결과값과 현재 분류해놓은 클래스랑 같은 경우 출력
  - 기울어진 이미지에 가장자리를 찾아서 원래대로 복구하는 코드 (바코드를 인식하는 경우가 있음)
- requirements.txt
  - 해당 코드를 돌리기 위해 필요한 라이브러리들
- test_img
  - 테스트용 이미지파일
