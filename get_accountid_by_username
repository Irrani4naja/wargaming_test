import requests
from hamcrest import assert_that

application_id = 'e02791f3148252b14c37e2169bf805e2'

def get_accountid_by_username(name) -> int:
    url = 'https://api.worldoftanks.ru/wot/account/list/?application_id=' + application_id+ '&search=' + name
    response = requests.get(url)
    assert_that(response.status_code == 200, 'Неверный код ответа страницы')
    json = response.json()
    userid = next(d['account_id'] for d in json['data'] if d.get('nickname') in name)
    print (userid)

get_accountid_by_username('test0')
