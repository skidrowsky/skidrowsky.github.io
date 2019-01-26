---
title: "mssql tcp/ip 연결 설정"
date: 2019-01-26 19:55:30 -0400
---

### SQL 서버 구성 관리자 화면에서 [SQL Server 네트워크 구성] 항목 설정
![TCP-IP속성](https://mblogthumb-phinf.pstatic.net/MjAxODA0MDZfMTI2/MDAxNTIyOTkwMzQxMDc1.R0-ViIL5SUSVYJ4c9NqqgiI8EaLgpWHRyc3l7N811Ksg.ZJakwUl0wck7FLKCWhhdRhyr4z3mmCRlnLtVNJMH8I4g.PNG.dktmrorl/2.PNG?type=w2)

### [TCP/IP] 항목을 더블클릭하면 아래와 같이 팝업창이 활성화됩니다. 해당 팝업에서 [TCP포트]를 1433으로 변경해주고 [확인] 버튼을 클릭.
![TCP포트](https://mblogthumb-phinf.pstatic.net/MjAxODA0MDZfMjg1/MDAxNTIyOTkwMzQxMTgx.F2NlrxAkPSr6uqIZIS-GG30onoIfVbPOztglwx8fkO8g.yBsN1KXi1qyousdUH7I5ITeUOZqAZyPyyL8-4KSmrNAg.PNG.dktmrorl/3.PNG?type=w2)

### MS SQL Server Management Studio를 실행합니다. 그리고 데이터베이스를 마우스 우클릭 후 [속성]으로 들어갑니다.
![Sql Database속성](https://mblogthumb-phinf.pstatic.net/MjAxODA0MDZfMjQ1/MDAxNTIyOTkxMzUxNjQ3.yWFaIOEE9dEySU5_AB628PJz6bK1c8TGd8zEHs5hoPYg.NTI9BGdvOn0q_iUR-bn35qHXZvyCNQCebO90vKr9K1cg.PNG.dktmrorl/6.PNG?type=w2)

### [보안] 항목을 클릭하여 [SQL Server 및 Windows 인증 모드]를 선택해줍니다.
![SQL Server 및 Windows 인증 모드](https://mblogthumb-phinf.pstatic.net/MjAxODA0MDZfMjI4/MDAxNTIyOTkxMzgyMzYy.YGMqM-nPkte8grImMnLup5Y7QNJcxslGTjyynvodNHgg.HZmXdO2bX3DFi5MOCEQ9AT8P4xVakBK48kILuR-Qzp0g.PNG.dktmrorl/5.PNG?type=w2)

### [연결] 항목을 클릭하여 [이 서버에 대한 원격 연결 허용]를 선택해줍니다.
![서버에 대한 원격 연결 허용](https://mblogthumb-phinf.pstatic.net/MjAxODA0MDZfMjA2/MDAxNTIyOTkxMzgyMjky._-wAXdeEkhpzoCBrjajY4NC5WL3Y7n9zPA5Q47cTnpYg.Z0QRq4l42VcroxVt8klgpdayKOMz5gVhe4UMjw9AJLgg.PNG.dktmrorl/4.PNG?type=w2)

### 만약 위과정을 모두 설정한 후에도 외부에서 DB접속이 안된다면, Windows 방화벽에서 인바운드 새규칙을 생성하여 1433번 포트를 허용해줍니다.



