```py
# clone
import os 
import subprocess

current_folder = os.getcwd()
print(current_folder)
'''
https://lab.ssafy.com/ddoriboy/django_hw_1_2
'''

USER_NAME = 'ddoriboy'
SUBJECT = input('과목을 입력해주세요. ex) django, db, js, vue : ')
DAY = input('날짜를 입력해 주세요. : ')
for sep in ['hw','ws']:
    # 만약 sep이 hw이면 2,4만 순회
    # 만약 sep이 ws이면 1~c까지 순회
    for stage in [1,2,3,4,5,'a','b','c']:
        BASE_URL = f'https://lab.ssafy.com/{USER_NAME}/{SUBJECT}_{sep}_{DAY}_{stage}'
        subprocess.run(['git', 'clone', BASE_URL])

# delete

# 자동으로 .git을 삭제하는 코드


import os
import subprocess

current_folder = os.getcwd()
print(current_folder)

# 현재 폴더의 모든 하위 폴더를 반복

for foldername, subfolder, filenames in os.walk(current_folder):
    print(foldername, subfolder, filenames)
    # root 디렉토리는 제외
    if foldername == current_folder: continue
    folder_path = os.path.join(foldername, '.git')
    subfolder.run(['rm', '-rf', folder_path])
    print(f'{folder_path} 폴더가 삭제 되었습니다.')
```