
# Rubaisha Aslam
# Assignment: 1
# To program this Windchill and Humidex Calculator, I have used user input, while loop, and conditionals such as if, elif and else statements.
# With this program we would be able to calculate the humidity and windchill to explain the effects of the weather.

# Start by adding a number constant
EULER_NUMBER = 2.71828

# Add a user input to add the temperature which will determine which loop it will take
AIR_TEMP = float(input("Enter a temperature between -50 and 50: "))

# Start a while loop so all the values are true and it will check all the if and elif statements to see what loop will be taken.
while True:
    # If value is above 50 or below -50, print statement will print
    if -50 > AIR_TEMP or AIR_TEMP > 50:
        print('That temperature is invalid.')
    # else if the value is equal or lower than 0 it will go into the loop
    elif AIR_TEMP <= 0:
        print('Calculating windchill.')
        wind_s = float(input('Enter a wind speed between 1 and 99 km/h: '))
        # if the wind speed is valid the loop will calculate the wind speed value but if the wind speed is not valid it will print "That wind speed is invalid."
        if 1 <= wind_s <= 99:
            # calculate the windchill and round it
            wind_chill = 13.12 + 0.6125 * AIR_TEMP - 11.37 * (wind_s ** 0.16) + 0.3965 * AIR_TEMP * (wind_s ** 0.16)
            wind_chill_rounded = round(wind_chill)
            # loop to see what is the exposure risk according to the windchill
            if -9 <= wind_chill <= 0:
                exposure_risk = 'Low risk.'
            elif -27 <= wind_chill <= -10:
                exposure_risk = 'Moderate risk.'
            elif -39 <= wind_chill <= -28:
                exposure_risk = 'High Risk. Skin can freeze in 10-30 minutes.'
            elif wind_chill <= -40:
                exposure_risk = 'Very High Risk. Skin can freeze in under 10 minutes.'

            # print statement for windchill value and exposure risk
            print("The windchill is {}.".format(wind_chill_rounded), end=' ')
            print("{}".format(exposure_risk))
        else:
            print('That wind speed is invalid.')
    # else if the temperature is equal or greater than 20 it will go into the loop
    elif AIR_TEMP >= 20:
        print('Calculating humidex.')
        dew_point = float(input('Enter the dewpoint between -50 and 50: '))
        # if the wind speed is valid the loop will calculate the dewpoint value but if the dewpoint is not valid it will print "That dew point is invalid."
        if dew_point <= AIR_TEMP:
            # calculate the dew point and round it
            F = 6.11 * (EULER_NUMBER ** (5417.7530 * (1 / 273.16 - 1 / (273.16 + dew_point))))
            G = 5 / 9 * (F - 10)
            hum_range = AIR_TEMP + G
            hum_range_rounded = round(hum_range)
            # loop to see what is the comfort rating according to the humidex
            if 20 <= hum_range_rounded <= 29:
                comfort_rating = 'Little or no discomfort.'
            elif 30 <= hum_range_rounded <= 39:
                comfort_rating = 'Some discomfort.'
            elif 40 <= hum_range_rounded <= 44:
                comfort_rating = 'Great discomfort. Avoid exertion.'
            elif hum_range_rounded >= 45:
                comfort_rating = 'Dangerous. Heat stroke possible.'
            # print statement for humidex and comfort rating
            print("The humidex is {}.".format(hum_range_rounded), end=' ')
            print("{}".format(comfort_rating))
        # print "That dew point is invalid.", if dewpoint is greater than temperature
        else:
            print("That dew point is invalid.")
    # else if statement if the temperature is greater than zero and less than twenty
    elif 20 > AIR_TEMP > 0:
        print('Windchill and humidex are not a factor at this temperature.')

    # user input and if statements to check another weather conditions
    ano_weather = input("Check another weather condition (Y/N)? ")
    if ano_weather.lower() == 'y':
        AIR_TEMP = float(input("Enter a temperature between -50 and 50: "))
    elif ano_weather.lower() == 'n':
        exit()
    else:
        print('That input is invalid.')
        AIR_TEMP = float(input("Enter a temperature between -50 and 50: "))
