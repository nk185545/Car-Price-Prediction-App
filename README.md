# Car-Price-Prediction-App

This application Predict the price of Car (which are already used by analysis some features) .

The App Link :    https://car-price-prediction-akd-app.herokuapp.com/

Some Glimpses of Application : 

![rcd1](https://user-images.githubusercontent.com/61588604/109003620-ae534c80-76cd-11eb-9fe5-c4ae51097af0.png)

![rcd2](https://user-images.githubusercontent.com/61588604/109003678-c1feb300-76cd-11eb-88ed-fc35eb7cb2d9.png)

![rcd3](https://user-images.githubusercontent.com/61588604/109003735-d2169280-76cd-11eb-91a4-87e819b7a86c.png)



Journey : 

*1) Data Collection* :  Data collected from the Kaggle . 

    *about data* : Data Columns are : Car_Name ,Year, Selling_Price, Kms_driven, Fuel_type , Seller_type, Transmission, Owner, Present_price. . 
    
    As a data scientist, we will predict the selling price for cars when user give some required input .
    
*2) Data Preprocessing :* 

        Data Preprocessing always is a great step to build Machine-Learning-Models .
        
        a) first of all , deleted "Car_Name" column, because there is no need for price predction .
        
        b) Year : this tells that when actually car was bought from showroom. So we can make a useful feature for price prediction. so make a new column named as "no_year" (number of years = current year - given year) and then deleted "Year" column. 
        
        c) Column "Fuel_type" contains following values : {"Petrol","Diesel","CNG"}, used *ONE-HOT_ENCODING* for converting this catagorical column into numerical column .
        
        d) Column "Seller_type" contains following values : {"Dealer","Individual"}, used *ONE-HOT_ENCODING* for converting this catagorical column into numerical column .
        
        e) Column "Transmission" contains following values : {"Manual Car","Automatic Car"}, used *ONE-HOT_ENCODING* for converting this catagorical column into numerical column .
        
        f) now there  is no null values and all data is in integer datatype.
        
        g) Now we can build machine learning models .
        
        

    
*3) Model building* : 

    a) split the dataset into X(independent features) and y(dependent features : "Present_Price" column) .
    
    b) perform train_test_split .
    
    c) try linear regression, RandomForestRegressor with hyperparameter tuning. 
    
    d) obsered that RandomForestRegressor with some parameters(got from hyperparameter tuning) has highest score and lowest error . so save this model using pickle.

*4) Model deployment* : 

    a) using flask framework , we deployed this model on HEROKU platform .
    
App link :  https://car-price-prediction-nk-app.herokuapp.com/
