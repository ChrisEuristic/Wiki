### SD Memory 포맷
1. https://www.sdcard.org/downloads/formatter/
2. SD Memory Card Formatter Download for Windows 다운로드
3. 본체에 SD Reader + SD Card가 결합된 상태에서 상기 Formatter 실행

### Raspberry Pi Imager 설치
1. https://www.raspberrypi.com/software/
2. 상기 웹사이트에서 Imager for Windows 다운로드
3. Imager.exe 설치
4. https://www.raspberrypi.com/software/operating-systems/
5. 웹사이트에서 Image with desktop and recommended software 다운로드.
6. Imager 실행
7. Choose OS 클릭
   .then(Use custom 클릭)
   .then(Image 파일(.img) 지정)
   .then(Mass Storage 어쩌고 클릭)
   .then(쭉쭉 넘어감)

### Raspberry Pi Wifi 연결 문제
* Country 설정을 영국(GB)으로 바꾸면 해결
1. pi@raspberry:~$ sudo vi /etc/wpa_supplicant/wpa_supplicant.conf
2. wpa_supplicant.conf 3번째줄 country=GB
3. WiFi 인터페이스 재실행
4. 리부팅하고 연결 확인
