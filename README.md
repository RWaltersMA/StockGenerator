# StockGenerator
This python app generates fictitious stock symbol data and stores it in two collections showcasing one document per data point vs fixed-based method of data storage in MongoDB  

# Useage
You will need to pip install pymongo and dnspython

The app takes the following parameters:

-s  Symbols   Defines the number of financial stock symbols to generate
-f  Fixed     (optional) If defined, specifies the number of data points each document should contain
-c  Connection Defiens the connection string to MongoDB (defaults to 

<b>Python3 realtime-mongo.py -s 5 -f 200 -c "mongodb://localhost"</b>

The application will run in perpetuity until you control-C, exit.

As data points are generated they (the same data point) will be written to two collections - StockData (one documnet per data point) and StockDataFixed (data written fixed based schema).

data can be viewed:

<b>db.StockData.findOne()
db.StockDataFixed.findOne()</b>

to see averages per security:

<b>db.StockData.aggregate([{
  _id: '$company_symbol',
  price: {
    $avg: {$avg: '$samples.price'}
  }
}])

db.StockDataFixed.aggregate([{
  _id: '$company_name',
  'price': {
    '$avg': { '$avg':'$samples.price'}
  }
}])
</b>

