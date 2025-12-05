_**Weather App - Flutter**_
A beautiful and functional multi-page Flutter weather application that provides real-time weather data using the OpenWeatherMap API.
  
	_**Features**_

•	 Real-time Weather Data: Get current weather information for any city
•	 City Search: Search for weather by city name
•	 GPS Location: Get weather for your current location
•	 Favorites: Save your favorite cities for quick access
•	 Settings: Toggle between Celsius and Fahrenheit
•	 UI: Modern and clean interface with gradient backgrounds
•	 Detailed Information: Temperature, humidity, wind speed, sunrise/sunset, and more
•	 Offline Storage: Favorites saved locally using SharedPreferences
•	 Auto-refresh: Reload weather data with pull-to-refresh
•	 Fast & Responsive: Optimized performance

		_**Installation**_

1.	Install dependencies
flutter pub get
2.	Get your OpenWeatherMap API Key
o	Sign up for a free account
o	Navigate to API Keys section
o	Copy your API key
3.	Add your API Key
o	Open lib/config/api_config.dart
o	Replace YOUR_API_KEY_HERE with your actual API key:
4.	static const String apiKey = 'your_actual_api_key_here';
5.	Run the app
flutter run

	 _**Project Structure**_

lib/
├── main.dart                      
├── config/
│   └── api_config.dart          
 where to put the API key  
├── models/
│   ├── weather_model.dart        
│   └── city_model.dart           
├── services/
│   ├── weather_api_service.dart 
│   ├── storage_service.dart      
│   └── location_service.dart     
├── providers/
│   ├── weather_provider.dart     
│   ├── favorites_provider.dart   
│   └── settings_provider.dart    
├── pages/
│   ├── home_page.dart            
│   ├── weather_details_page.dart
│   ├── favorites_page.dart       
│   └── settings_page.dart       
├── widgets/
│   ├── weather_card.dart         
│   ├── weather_detail_item.dart  
│   ├── favorite_city_card.dart   
│   ├── loading_widget.dart       
│   └── error_widget.dart         
├── utils/
│   ├── constants.dart           
│   └── helpers.dart             
└── routes/
    └── app_routes.dart           

 	_**Dependencies**_


dependencies:
  flutter:
    sdk: flutter
  provider: ^6.1.1              # State management
  http: ^1.1.0                  # HTTP requests
  shared_preferences: ^2.2.2    # Local storage
  intl: ^0.18.1                 # Date formatting
  geolocator: ^10.1.0           # GPS location
  geocoding: ^2.1.1             # Reverse geocoding
  cupertino_icons: ^1.0.2       # iOS icons

		 _**API Usage**_


OpenWeatherMap Current Weather API
Endpoint: https://api.openweathermap.org/data/2.5/weather
Parameters:
•	q: City name (e.g., "London")
•	lat & lon: Coordinates for GPS
•	appid: Your API key
•	units: "metric" (Celsius) or "imperial" (Fahrenheit)
Example Response:
{
  "name": "London",
  "main": {
    "temp": 15.5,
    "feels_like": 14.2,
    "humidity": 72
  },
  "weather": [{
    "main": "Clouds",
    "description": "broken clouds",
    "icon": "04d"
  }],
  "wind": {
    "speed": 3.6
  }
}
		 _**Features Breakdown**_
		 
1. Home / Search Screen
•	Search for any city worldwide
•	Display current weather in a beautiful card
•	GPS button for current location
•	Navigate to detailed weather view
2. Weather Details Screen
•	Large weather icon from API
•	Current temperature and "feels like"
•	Weather description
•	Detailed metrics (humidity, wind, pressure, visibility)
•	Sunrise and sunset times
•	Min/max temperatures
•	Add/remove from favorites
3. Favorites Screen
•	List of all saved favorite cities
•	Click to view weather details
•	Delete individual favorites
•	Clear all favorites option
•	Empty state with guidance
4. Settings Screen
•	Temperature unit toggle (°C / °F)
•	About app information
•	API configuration help
•	Reset settings option


		 _**State Management**_


This app uses Provider for state management with three main providers:
1.	WeatherProvider: Manages weather data and API calls
2.	FavoritesProvider: Handles favorite cities list
3.	SettingsProvider: Controls app settings (temperature unit)

		_** Data Persistence**_


•	SharedPreferences for storing: 
o	Favorite cities list
o	Temperature unit preference
o	Last searched city

		_** Error Handling**_


•	Network errors (no internet connection)
•	Invalid city names (404 errors)
•	API key errors (401 unauthorized)
•	GPS permission denied
•	Loading states with indicators

		_** Building APK **_


Debug APK
flutter build apk --debug
Release APK
flutter build apk --release
APK location: build/app/outputs/flutter-apk/app-release.apk
🐛 Troubleshooting
API Key Issues:
Build Errors
flutter clean
flutter pub get
flutter run
________________________________________

