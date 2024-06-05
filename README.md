# ISS Overhead Notification Script

This Python script checks if the International Space Station (ISS) is currently overhead at a specified location and sends an email notification if it is night time. The script runs continuously, checking the conditions every minute.

## Features

- Retrieves the current location of the ISS.
- Checks if it is night time at the specified location.
- Sends an email notification if the ISS is overhead and it is night time.

## Prerequisites

- Python 3.x
- Internet connection
- A Gmail account for sending email notifications

## Installation

1. Clone this repository or download the script file.

2. Install the required Python libraries:
    ```bash
    pip install requests
    ```

## Usage

1. Open the script file and update the following variables with your own information:
    ```python
    MY_LAT = 36.817421  # Your latitude
    MY_LONG = 10.151432  # Your longitude
    my_email = "your_email@gmail.com"  # Your email address
    password = "your_email_password"  # Your email password
    ```

2. Run the script:
    ```bash
    python iss_overhead_notifier.py
    ```

The script will check every minute if the ISS is overhead and if it is night time. If both conditions are met, it will send an email notification to the specified email address.

## Code Explanation

- **Import Libraries**: The script uses `smtplib` for sending emails, `requests` for making HTTP requests, and `datetime` for handling date and time.
- **Define Location and Email**: Specify the latitude and longitude of the location and the email credentials.
- **Check ISS Position**: The `iss_overhead` function checks if the ISS is within 5 degrees of the specified location.
- **Check Night Time**: The `is_night` function checks if it is currently night time at the specified location using the sunrise-sunset API.
- **Main Loop**: The script runs an infinite loop that checks the conditions every 60 seconds and sends an email if both conditions are met.

## Security Considerations

- **Email Credentials**: Be cautious with your email credentials. It is recommended to use environment variables or a secure vault for storing sensitive information.
- **APIs Used**: The script uses publicly available APIs (`http://api.open-notify.org/iss-now.json` and `https://api.sunrise-sunset.org/json`) for retrieving ISS location and sunrise-sunset times.

## Acknowledgments

- [Open Notify](http://open-notify.org/) for the ISS location API.
- [Sunrise-Sunset API](https://sunrise-sunset.org/api) for providing sunrise and sunset times.
