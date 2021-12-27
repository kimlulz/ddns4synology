# Use Gandi LiveDNS from Synology NAS box - KOR TRANSLATION
Source - https://github.com/kofemann/livedns4synology
# 시놀로지에서 Gandi LiveDNS 사용하기
[LiveDNS RESTful API][1] 기반.
이 프로젝트는 시놀로지 NAS에서 [Gandi.net](https://www.gandi.net/en) 도메인을 통한 동적 DNS(DDNS)기능을 제공하기 위해 시작되었습니다.
* 헤놀로지에서도 정상작동    

![화면 캡처 2021-12-27 134012](https://user-images.githubusercontent.com/42508318/147435142-2f7e7b58-a395-4653-a35e-1549028b6271.png)

## 설치
1. 시놀로지 패키지 센터에서 python3 설치
2. SSH 접속 후 하기 명령어로 스크립트 다운로드 후 실행 파일로 만들기
```
$ sudo curl -o /usr/local/bin/livedns.py https://raw.githubusercontent.com/kofemann/livedns4synology/master/livedns.py
$ sudo chmod +x /usr/local/bin/livedns.py
```
3. 에디터로 /etc.defaults/ddns_provider.conf에 Gandi LiveDNS 추가
```
[Gandi LiveDNS]
        modulepath=/usr/local/bin/livedns.py
        queryurl=Gandi
```
> 참고 : 7.0버전부터는 항목 이름 앞에 `USER_` 붙여야 함!! > [USER_Gandi LiveDNS]     
DSM 접속 -> 외부 액세스 -> DDNS -> 추가 에 Gandi LiveDNS 항목이 표시되어야 함    

## 설정
1. 풀 도메인 (web forward 및 ssl 발급으로 등록한 도메인 ex) nas.kimlulz.io)    
1. 사용자 이름 (상관없다고는 하는데 DNS 사이트 아이디로..)    
1. 발급한 API key (패스워드/키 항목에 넣어주세요)    

## License

This work is published under [public domain](https://creativecommons.org/licenses/publicdomain/) license.

[1]: https://api.gandi.net/docs/livedns/
