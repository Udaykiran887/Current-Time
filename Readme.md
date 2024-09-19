---
# Current Time App - TimeZoneDB API Integration

## Project Overview
The **Current Time App** is a simple Node.js (or Node-RED) application that uses the [TimeZoneDB API](http://timezonedb.com) to retrieve the current time for any selected time zone. This project allows users to query the time for a specific zone and format the response data, including details such as the country, GMT offset, and daylight saving time (DST) status.

### Features:
- Retrieve current time for any time zone.
- Display formatted information, including the time zone abbreviation, country name, and GMT offset.
- Can be used in applications that require time zone awareness and localization.

---

## Installation Instructions

To run this project, follow the steps below:

### Prerequisites
- Node.js installed on your machine (for Node.js environment).
- Node-RED installed (if you're using it to visualize the flow).
- A valid API key from [TimeZoneDB](https://timezonedb.com).

### Steps:

1. **Clone the repository**:
    ```bash
    git clone https://github.com/yourusername/current-time-app.git
    cd current-time-app
    ```

2. **Install dependencies**:
    If you are using Node.js, ensure that you install the required libraries:
    ```bash
    npm install axios
    ```

3. **Environment Configuration**:
   Create a `.env` file to store your TimeZoneDB API key. Example:
   ```bash
   TIMEZONE_API_KEY=ZDR9FU8IAY42
   ```

4. **Run the application**:
   To fetch the current time for a specified zone:
   ```bash
   node app.js
   ```

   You can also use this in a Node-RED flow by configuring an HTTP Request node to query the API.

---

## API Integration Usage

### TimeZoneDB API Integration
This project integrates with the [TimeZoneDB API](http://timezonedb.com) to fetch the current time based on the specified zone.

### API Endpoint:
- **Base URL**: `http://api.timezonedb.com/v2.1/get-time-zone`
- **Method**: `GET`

### Example API Call:
```bash
http://api.timezonedb.com/v2.1/get-time-zone?key=ZDR9FU8IAY42&format=json&by=zone&zone=Asia/Taipei&time=1726753290
```

### Parameters:
- `key`: Your API key (e.g., `ja93bwg3i02nvej`)
- `format`: The response format, `json` in this case.
- `by`: The method to retrieve time zone information. In this case, it's `zone`.
- `zone`: The time zone identifier (e.g., `Asia/Taipei`).
- `time`: (Optional) Unix timestamp to get the time at a specific moment.

### Sample Response:
```json
{
  "status": "OK",
  "message": "",
  "countryCode": "TW",
  "countryName": "Taiwan",
  "zoneName": "Asia/Taipei",
  "abbreviation": "CST",
  "gmtOffset": 28800,
  "dst": "0",
  "zoneStart": -2147483648,
  "zoneEnd": null,
  "nextAbbreviation": null,
  "timestamp": 1726753290,
  "formatted": "2024-09-19 23:06:57"
}
```

You can extract the following data from the response:
- **Formatted Time**: The current local time in the specified zone (`formatted`).
- **Country Name**: The name of the country for that time zone (`countryName`).
- **GMT Offset**: The offset in seconds from GMT (`gmtOffset`).
- **Daylight Saving Time**: Whether DST is active (`dst`).

---

## Contributing
Contributions are welcome! To contribute:

1. Fork the repository.
2. Create a new feature branch.
3. Commit your changes.
4. Push your branch.
5. Create a Pull Request.

Please follow the coding style used in the project and ensure that your contribution passes any tests before submitting a pull request.

---

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## Contact Information
For any inquiries, feel free to reach out:

- **Email**: udaykirankothagattu@gmail.com
- **GitHub**: [uday kiran kothagattu](https://github.com/udaykiran887)
---
