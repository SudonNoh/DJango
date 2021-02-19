# DJango

## mysqlclinet 설치가 안되는 경우

- 가상환경에서 sudo yum install python3-devel
- yum install -y mariadb-devel gcc


## Pycharm 으로 만든 가상환경에서 Django Runserver 실행 방법

1) Pycharm Project 폴더 경로 검색
2) Pycharm Project 경로 내에서 Project명/venv/bin 에 진입
3) source activate
4) Pycharm Project 내에 manage.py 파일이 있는 곳에서 python3 manage.py runserver 0:8000 실행

## IE 문서 모드란(meta http-equiv="x-ua-compatible" content="IE=edge")
content="IE=edge"는 IE브라우저에서, 각 버전 중 가장 최신 표준 모드를 선택하는 문서 모드

## on_delete.CASCADE
Cat_ID = models.ForeignKey(Catalog_info, on_delete=models.CASCADE, db_column='C_ID')   
Catalog_info 테이블에서 레코드가 삭제되는 경우 그 레코드에 연결된 Cat_ID 도 삭제됨
Foreignkey 는 제약조건으로 사용하고 join을 활용해야함
