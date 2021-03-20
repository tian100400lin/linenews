#   notify - line - dev - news
[ LINE   Developer   news ](https://developers.line.biz/ja/news/)이 갱신되었을 때 LINE Notify로 통지하는 스크립트

cron을 설정하면 최신 정보를 빠르게 LINE으로 알릴 수 있다.

##   Setup
``` bash
$   pip   install   - r   requirements . txt
$   cp   . env . sample   . env
```

##   Step 1
[여기] (https://notify-bot.line.me/my/)에서 LINE에 로그인하여 알리고 싶은 토크룸을 선택하여 토큰 발급.

**Setup**에서 작성한 `.env`의 `NOTIFY_TOKEN`에 토큰을 기재.  
데이터베이스명을 변경하고 싶을 때는 'DB_FILE_PATH'를 변경.

``` bash
DB _ FILE _ PATH = " news . sqlite "
NOTIFY _ TOKEN = " iEET 2 ScqVhKrt 45 ZTXXXXXXXXXXXX "
```

##   Step 2
실행하다.
``` bash
$   python 3   notice.py
```

## 주의
첫 실행은 데이터베이스에 데이터가 없기 때문에 연속해서 많은 통지가 온다.  
그 때문에, `./news_notify/news/config.py`에 `NOTIFY_SPAN`을 마련하고 있다.  
이 값을 바꿔 쓰면 지정한 초마다 알림을 할 수 있다.

``` python
NOTIFY _ SPAN   =   0
```

##   Lint
-   black
-   flake 8
