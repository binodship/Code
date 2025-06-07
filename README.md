# Code
Web url code to insider vs code

import requests

url = "http://127.0.0.1:5500/files"  # The base URL of your live server

try:
    response = requests.get(url)
    response.raise_for_status()  # Raise an exception for bad status codes (4xx or 5xx)

    print("Successfully connected to the live server!")
    print("Status Code:", response.status_code)
    print("Content:")
    print(response.text)  # Print the HTML content of the homepage

except requests.exceptions.RequestException as e:
    print(f"Error connecting to the live server: {e}")

# You can also access specific resources served by the live server:
specific_resource_url = "http://127.0.0.1:5500/your_file.html"  # Replace with an actual file path
try:
    specific_response = requests.get(specific_resource_url)
    specific_response.raise_for_status()
    print(f"\nContent of {specific_resource_url}:")
    print(specific_response.text)
except requests.exceptions.RequestException as e:
    print(f"Error fetching {specific_resource_url}: {e}")
