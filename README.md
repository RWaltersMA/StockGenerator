# StockGenerator
This python app generates fictitious stock symbol data and stores it in two collections showcasing one document per data point vs fixed-based method of data storage in MongoDB  

# Useage
You will need to pip install pymongo and dnspython

The app takes the following parameters:

-s  Symbols   Defines the number of financial stock symbols to generate
-f  Fixed     (optional) If defined, specifies the number of data points each document should contain
-c  Connection Defiens the connection string to MongoDB (defaults to 

Python3 realtime-mongo.py -s 5 -f 200 -c "mongodb://localhost"

The application will run in perpetuity until you control-C, exit.
