# wikibaseIntegrator_new

## 1. 가상환경 생성 및 접속
- `conda create -n wikibase python=3.7`
- `conda activate wikibase`
## 2. git clone
https://github.com/wikimedia/pywikibot
## 3. clone한 폴더 안에 ipynb 파일 생성하기
ipynb kernel도 terminal의 kernel과 동일하게 맞춰주기. 만약에 연결할 수 없다고 뜨면, 다음과 같은 절차로 remove하고 다시 설정하기
```python
conda remove --name wikibase_0804 ipykernel
conda install -n wikibase_0804 ipykernel --update-deps
```
## 4. clone한 폴더 파일 설정
### 4.0. 설치하기
- `pip install requests`
- cd pywikibot 후 `pip install -r requirements.txt`
- `git submodule update --init`
- `python pwb.py login -all`: mediawiki, mediawiki, username은 로그인한 아이디 이름으로, botname은 웹에서 생성한 botname으로, botpassword는 bot 생성했을 때 발급되는 비밀번호로 넣어주기
### 4.1. user-config.py
- family_files['mediawiki'] = 'http://localhost:4200/' 추가하기
- password_file 경로 설정하기
### 4.2. user-password.py
형식 잘못되어 있을 경우 아래와 같은 형식으로 바꿔주기
```python
('Admin', BotPassword('jylBot', 'o89upbvh9hgrpofql7kbc6g3n55jabc6'))
```
### 4.4. pywikibot/pywikibot/config.py
user_config_file 변수에 get_user_confifg_file() 함수 쓰지 말고 user-condig.py 경로로 바꿔주기
