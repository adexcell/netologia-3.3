from urllib.parse import urlencode
import requests

APP_ID = 6870940
AUTH_URL = 'https://oauth.vk.com/authorize'
auth_data = {
	'client_id': APP_ID,
	'display': 'page',
	'scope': 'friends, offline',
	'response_type': 'token',
	'v': '5.92', 
}
print('?'.join((AUTH_URL, urlencode(auth_data))))

token = 'a1ad5787028211319e2ae8a8b981d5989c37abfff0c12666752f7a3022bbe5af4733ead48d3f2061d0334'

class User(object):
	def __init__(self, user_id):
		self.user_id = user_id

	def __str__(self):
		return 'Ссылка на профиль: https://vk.com/id' + str(self.user_id)

	def __and__(self, other):
		params = {
		'v': '5.92',
		'access_token': token,
		}
		response = requests.get('https://api.vk.com/method/friends.getMutual?source_uid=' + user1.user_id + '&target_uid=' + user2.user_id, params)
		friends_list = response.json()
		exemler_friends = []
		for i, friend in enumerate(friends_list["response"]):
			exemler_friends.append(User(friend))
		print(f'Список id общих друзей: {friends_list["response"]}')

user1 = User('164812421')
user2 = User('292495343')

print(user1)
user1 & user2
