#PREVENT - Community resources generated from Yelp


#Business Details     URL -- 'https://api.yelp.com/v3/businesses/{id}'
#Business Reviews     URL -- 'https://api.yelp.com/v3/businesses/{id}/reviews'
#Business Search      URL -- 'https://www.yelp.ca/developers/documentation/v3/business_search'

#See Document for list to desired app categories 

#Businesses, Total, Region

import json

#Define a business ID
#Define my API Key, My Endpoint, and My Header
from pip._vendor import requests

API_KEY = 'enter your api key here'
ENDPOINT = 'https://api.yelp.com/v3/businesses/search'
HEADERS = {'Authorization': 'bearer %s' % API_KEY}


#desired location set at Barnes Jewish Hospital 
#latitude 38.637343
#longitude -90.264325
#Radius is set at the maximum value of 400000 meters or 25 miles

#Define my parameters of the search
#BUSINESS SEARCH PARAMETERS - EXAMPLE
PARAMETERS = {'term': 'grocery',
              'limit': 50,
              'offset': 50,
              'radius': 40000,
              'latitude': '38.637343', 'longitude': '-90.264325'}
            

#substitute 'grocery' for other category names
#see list of resource categories to populate app 


#Make a request to the Yelp API
response = requests.get(url = ENDPOINT,
                        params = PARAMETERS,
                        headers = HEADERS)

#Conver the JSON String
business_data = response.json()

#print the response
print(json.dumps(business_data, indent = 3))
