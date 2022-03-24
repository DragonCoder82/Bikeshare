import calendar
import time
import pandas as pd
import numpy as np

df = pd.read_excel ("C:\python\washington.xlsx")
df = pd.read_excel ("C:\python\chicago.xlsx")
df = pd.read_excel ("C:\python\new_york_city.xlsx")


CITY_DATA = { 'chicago': 'chicago.csv',
              'new york city': 'new_york_city.csv',
              'washington': 'washington.csv' }

months = ['january', 'february', 'march', 'april', 'may', 'june', 'july', 'august', 'september', 'october', 'november', 'december']
DAYS = ['monday', 'tuesday', ' wednesday', 'thursday', 'friday', 'saturday', 'sunday']
cities = ['chicago', 'new york city', 'washington']

def get_filters():
    """
    Asks user to specify a city, month, and day to analyze.

    Returns:
        (str) city - name of the city to analyze
        (str) month - name of the month to filter by, or "all" to apply no month filter
        (str) day - name of the day of week to filter by, or "all" to apply no day filter
    """
    print('Hello! Let\'s explore some US bikeshare data!')
    # TO DO: get user input for city (chicago, new york city, washington). HINT: Use a while loop to handle invalid inputs

    while True:
        city = input('Please choose a city one of the following cities: Chicago, New York City, and Washington:\n>>> ').lower()
        if city not in cities:
            print('"{}" is currently not a city we have information on.'.format(city))
            continue
        else:
            break

    while True:
        month = input('Please enter the month you would like more information on:\n>>> ' ).lower()
        if month not in months:
            print('"{}" is not a valid month. Please try again.' .format(month))
            continue
        else:
            break

    while True:
        day = input('Please enter the day you would like more information on:\n>>> ', ).lower()
        if day not in DAYS:
            print('"{}" is not a valid day. Please try again.'.format(day))
            continue
        else:
            break


    print('-'*40)
    return city, month, day

def load_data(city, month, day):
    """
    Loads data for the specified city and filters by month and day if applicable.

    Args:
        (str) city - name of the city to analyze
        (str) month - name of the month to filter by, or "all" to apply no month filter
        (str) day - name of the day of week to filter by, or "all" to apply no day filter
    Returns:
        df - Pandas DataFrame containing city data filtered by month and day
    """





def time_stats(df):
    """Displays statistics on the most frequent times of travel."""

    print('\nCalculating The Most Frequent Times of Travel...\n')
    start_time = time.time()

    # TO DO: display the most common month
    common_month = df['month'].mode()[0]
    print('Most Common Month: ', calendar.month_name[common_month])

    # TO DO: display the most common day of week
    common_week = df['week].mode()[0]
    print('Most Common Week: ', calendar.week_name[common_week])

    # TO DO: display the most common start hour
    common_hour = df['hour'].mode()[0]
    print('Most Common Hour: ', calendar.hour_name[common_hour])

    print("\nThis took %s seconds." % (time.time() - start_time))
    print('-'*40)
