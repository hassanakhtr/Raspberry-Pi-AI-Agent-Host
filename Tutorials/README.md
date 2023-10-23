# Raspberry Pi AI Agent Host


## Simplified Summary

 The AI Agent Host can be complex given that it involves several aspects such as AI, edge computing, Docker, and Raspberry Pi. Let me attempt to simplify it:  

The AI Agent Host is essentially a setup that allows you to run AI applications directly on a Raspberry Pi, which is a small, low-cost computer often used in various tech projects.  

The AI Agent Host functions as a "host" for an AI "agent". These applications can interact with live data, coming from either online sources (APIs) or the Raspberry Pi's own sensors, to make decisions or predictions.  

Moreover, the AI Agent Host is designed to be modular, which means you can add or remove different components depending on what your project needs. For example, if you need a specific database or visualization tool, you can add it to the setup.  

Also, you can use this setup in combination with a powerful GPU server. So, if you have tasks that are too demanding for the Raspberry Pi, you can send them to this server for processing. This is made possible with the inclusion of CodeServer and remote connection to a JupyterHub installed on the GPU server.  

Finally, the AI Agent Host uses lightweight services like QuestDB and Grafana, suitable for the Raspberry Pi's limited resources, and is optimized for DietPi, a lightweight operating system ideal for single-board computers like Raspberry Pi.  

I hope this explanation helps simplify the concept of the AI Agent Host. If you have any further questions or if something is still unclear, feel free to ask!  

## Features

The AI Agent Host, designed specifically for AI development, offers several key features making it an ideal solution for Raspberry Pi 4 with 8GB RAM, especially when running DietPi OS:

1. **Modular Environment**: The AI Agent Host is built as a module-based system, allowing different components to be added or removed based on the requirements of the project. This is perfect for the customizable nature of Raspberry Pi. Furthermore, by adding an AI Agent container, the AI Agent Host can be transformed into an AI Agent Lab, expanding its capabilities for AI development and experimentation.

2. **Live Data Interaction**: With the ability to work with live data from both APIs and Raspberry Pi's own sensors, AI Agent Host becomes a powerful tool for real-time data analysis, modeling, and decision-making.

3. **Lightweight Services**: Services like QuestDB and Grafana used in the AI Agent Host are lightweight yet robust, making them suitable for the Raspberry Pi's limited hardware resources compared to larger servers.

4. **Remote Development Capabilities**: The inclusion of Code-Server allows you to connect to a remote JupyterHub installed on a powerful GPU Server when necessary, using Raspberry Pi as the Docker host.

5. **Data Handling and Visualization**: QuestDB for efficient data handling and Grafana for intuitive data visualization are integral for any AI and machine learning projects.

6. **Optimized for DietPi**: The AI Agent Host's compatibility with DietPi, a lightweight OS optimized for single-board computers like Raspberry Pi, ensures efficient use of the Raspberry Pi's hardware resources.

7. **Community Support**: With active communities for both Raspberry Pi and AI Agent Host, you can expect robust support and resources for your AI development projects.

These features make the AI Agent Host a dynamic, effective, and efficient environment for AI development on a Raspberry Pi 4 with 8GB RAM, especially for projects involving real-time or sensor data.


## AI Agent Host: A Novel Approach to Edge Computing

The AI Agent Host offers an innovative setup, connecting edge devices like the Raspberry Pi to a JupyterHub on a remote GPU server. This unique configuration, part of a broader trend known as edge computing, enables real-time data analysis and decision-making on the edge while offloading computationally intensive tasks to a GPU server in the cloud.

While this specific setup is not commonly seen or standardized, it adds significant value to fields that require real-time data analysis and decision-making capabilities at the edge. Potential applications include autonomous vehicles, Internet of Things (IoT), robotics, and more.

One of the primary challenges in edge computing is developing an infrastructure that allows for seamless communication and integration between edge devices and cloud servers. The AI Agent Host provides a powerful solution to this challenge, offering a framework that could potentially standardize these interactions.

As the AI industry continues to evolve rapidly, this innovative approach may become more commonplace. The AI Agent Host is at the forefront of this technological development, paving the way for new use cases and implementations.

Please note that while we strive to keep this document up-to-date, the field of AI is continuously evolving. For the latest information and developments, we recommend staying active in relevant online communities and keeping up with the latest research.

# Notebooks

## AI Agent Host: Data Science Notebooks

The AI Agent Host offers a robust interface for managing and querying data, real-time visualization, and coding. The goal is to supplement this with a suite of notebooks tailored for specific applications in the realm of data science.

### Proposal

We are planning to develop a suite of data stream processing notebooks alongside machine learning notebooks tailored for the AI Agent Host. These notebooks are aimed to cater to specific domains like AI Human Interface, Computer Vision, Healthcare, Vehicle Tracking, and Weather Stations. They will furnish users with curated data sources and machine learning templates, streamlining the experimentation process.

### Data Sources

The available data sources are categorized based on domains:

- **AI Human Interface**:
     - Integration with cameras and microphones for real-time human interaction data.
     - Natural language processing to decipher human emotions, intentions, and commands.

- **Computer Vision**:
    - Access to public image datasets for object detection, facial recognition, etc.
    - Tools for image processing and analysis.

- **Healthcare**:
    - Data from health monitoring devices like wearables capturing heart rate, sleep patterns, etc.
    - Patient data repositories and Electronic Health Records (EHRs).

- **Vehicle Tracking**:
    - Telematics data from on-board vehicle sensors, recording speed, location, and diagnostics.
    - Traffic and route data for real-time navigation and traffic prediction.

- **Weather Station**:
    - Real-time data feeds from weather sensors like temperature, humidity, pressure, etc.
    - Historical weather data repositories for trend analysis and prediction.

- **Market Data**:
    - Live stock prices, commodities data, and forex rates.
    - Historical trade data and financial indicators for diverse markets.
    - News streams related to financial markets.

- **General Data Streams**:
    - Public datasets from Kaggle or UCI Machine Learning Repository.
    - Streaming platforms like Twitter API.
    - Web scraping utilities to extract data from varied online sources.

### Machine Learning Templates

For each domain, we will offer specific machine learning templates:

- **AI Human Interface**: Chatbots, sentiment analysis, emotion detection.
- **Computer Vision**: Image classification, object detection, scene understanding.
- **Healthcare**: Predictive analytics, disease detection, health trend analysis.
- **Vehicle Tracking**: Route optimization, vehicle health diagnostics, traffic prediction.
- **Weather Station**: Weather trend analysis, prediction models for climate changes, rain prediction.
- **Market Data**: Algorithmic trading strategies, risk analysis, market sentiment analysis.

1. **Coinbase**
## Real-time Synchronization of Coinbase Trades to QuestDB using WebSockets in Python

This script achieves real-time synchronization between Coinbase, a popular cryptocurrency exchange, and QuestDB, a high-performance, time-series database. Initially, it establishes a connection to Coinbase's Websocket feed and subscribes to match events for BTC-USD and ETH-USD trading pairs. Concurrently, it connects to a QuestDB instance running on a Docker host. If not already present, a table named 'coinbase_matches' is created to store trading match details. The script continuously listens for new data from Coinbase, and upon receiving, inserts the data into the 'coinbase_matches' table in QuestDB. If the websocket connection closes unexpectedly, it attempts a reconnection. Additionally, if any other unexpected errors occur during data retrieval or insertion, the script prints the error for debugging purposes.

## Real-time Synchronization of Coinbase Trades to QuestDB using QuestDB with Producer/Consumer Pattern in Julia Notebook.
The Julia notebook sets up a producer/consumer pattern to build a cryptocurrency trade database using QuestDB. The Trade struct is created to store trade data, with a RemoteChannel (from the Distributed package) created to store trades. The WebSocket feed from CoinbasePro is connected, and the relevant fields from incoming JSON objects are parsed and stored as trades in the RemoteChannel. The notebook sets up a QuestDB connection and creates a table with the columns corresponding to the Trade struct. A consumer process reads from the RemoteChannel and writes data to the QuestDB table. The end result is a database of trades that can be queried for further analysis.

Set up parameter:


```
using Sockets
function save_trades_quest(trades)
    cs = connect("docker_host_ip_address", 9009)
    while true
        payload = build_payload(take!(trades))
        write(cs, (payload))
    end
    close(cs)
end
```

1. Remember to replace **<docker_host_ip_address>** with the actual IP address of the Docker host where your server is running.

2. Update the jupyter extension to the pre-release version and then click on the reload button.

3. To establish a remote JupyterHub connection from code-server, refer to this [Tutorial](https://code.visualstudio.com/docs/datascience/jupyter-notebooks#_connect-to-a-remote-jupyter-server) for guidance. Create an [API token](https://jupyterhub.readthedocs.io/en/stable/howto/rest.html#create-an-api-token) and use the provided URL:

```
https://<your-hub-url>/user/<your-hub-user-name>/?token=<your-token>
```

3. Configure port forwarding.

 If you are using JupyterHub on a remote server, you'll need to configure port forwarding either on the server itself or on any intermediate network devices, such as routers or firewalls.

- **Server-level port forwarding**: Configure port forwarding on the server so that it forwards incoming connections on port 9009 to the Docker host's IP address and the same port (9009).

- **Network device port forwarding**: If there are intermediate network devices between the JupyterHub server and the Docker host, configure port forwarding on these devices to route traffic from the desired source IP and port to the Docker host's IP and port (9009).

After configuring the port forwarding, you should test it. You can do this by attempting to connect to the Docker host's IP address on port 9009 from the JupyterHub server. For example, you can use the following command:

```
telnet docker_host_ip_address 9009

```

Remember to replace **<docker_host_ip_address>** with the actual IP address of the Docker host where your server is running.


3. Run the Data Stream Processing Notebook

Click on the '**Run All**' button in the toolbar and then check the Grafana dashboard for real-time visualization of market data.



## SQL Queries for Real-Time Analytics and Aggregations on Trades Table in QuestDB
SQL query written for QuestDB, a time-series database optimized for high-performance querying and real-time analytics. The queries select data from a "trades" table, specifically focusing on the timestamp, price, and size columns. They perform various aggregations such as capturing the first price for each 1-second interval for Ethereum (ETH) and Bitcoin (BTC), as well as summing up the trading volume (size) for Ethereum (ETH). The WHERE clause filters the dataset to include only trades for the symbols "ETH-USD" and "BTC-USD" with timestamps within the last day. The queries sample the data in 1-second intervals, aligned to the calendar, making them ideal for high-frequency time-series analysis. The result set includes columns for the Ethereum and Bitcoin prices and also provides the summed trading volume for Ethereum.

## Grafana Dashboard for Time-Series Data Visualization of ETH (Ethereum) and BTC (Bitcoin) with QuestDB Data Source and SQL Query
JSON dashboard file for Grafana, a platform for monitoring and visualizing metrics from various data sources. The dashboard has an ID of 1 and showcases time-series data for both ETH (Ethereum) and BTC (Bitcoin). The data is pulled from a QuestDB data source with the use of SQL queries that fetch metrics like real-time prices for the past 24 hours. The dashboard features two panels: one for displaying the prices of ETH and BTC, and another focusing on the price and volume of ETH.  

 ![dashboard coinbase](../notebooks/market-data/coinbase/dashboard-coinbase.png)

1. **Vehicle-Tracking**

##  Quectel EG25/EC25 Mini PCIe 4G/LTE  GPS Tracker

### Overview

This script is designed to interact with the Quectel EG25/EC25 Mini PCIe 4G/LTE GPS module to retrieve GPS location data and store it in a QuestDB database. It establishes a connection to the database, creates a table if it doesn't exist, and sets up the serial communication with the GPS module. The script continuously queries the GPS module for its information using AT commands and extracts relevant GPS parameters such as latitude, longitude, altitude, speed, and timestamp. These parameters are then transformed and formatted for better readability. The latitude and longitude values are calculated from degree and minute components and stored in the database along with other extracted information. Any errors encountered during the process are gracefully handled, and the serial port and database connection are properly closed at the end. The script offers an efficient and reliable way to capture and manage GPS data from the EG25/EC25 4G HAT GPS module

###  Set up parameter:

After installing the AI Agent Host, open VS Code in your browser through an HTTPS connection. 

Navigate to `>project/vehicle-tracking/data-stream-processing.py`.
The script is pre-configured to connect to a QuestDB instance using the following credentials:

```
dbname="qdb",
user="admin",
password="quest",
host="yourdomain.tld",
port="8812"
```

Remember to replace **<yourdomain.tld>** with the actual domain name that points to the IP address of the Fixed IP SIM Card where your Raspberry Pi is running.

### GPS Tracker Data query

```
-- Retrieve the timestamp and data values: latitude, longitude, altitude, speed.

SELECT
    timestamp,        -- Select the timestamp of the data
    data              -- Select the data value
FROM  
    gps_data      -- From the 'gps_data' table
WHERE 
    timestamp > dateadd('d', -1, now()); -- Only select data from the past 24 hours

```

This Grafana query retrieves the timestamp and corresponding data values from the **gps_data** table. It's specifically designed to only fetch data from the last 24 hours, ensuring that dashboard viewers are presented with the most recent day's data trends. By focusing on this short timeframe, users can gain insights into daily data fluctuations and patterns, which can be especially valuable for real-time monitoring or short-term data analysis.



### Run Python File in Terminal:
Execute the Python script from the terminal to start collecting gps data.


### Connect to Grafana Dashboard:
Open your browser and navigate to the Grafana interface. Select the GPS Tracker dashboard to start monitoring your data in real-time



![GPS Tracker Dashboard](../notebooks/market-data/vehicle-tracking/gps_tracker_dashboard.png)


### Customizing the GPS Tracker:

While the pre-configured GPS tracker setup is designed to work out of the box, you can also customize it to match your unique requirements. Here are some steps to consider when customizing the setup:

- **Modify Data Stream Processing**: The Python script responsible for processing GPS data can be customized to include additional data points or calculations. For example, you could include data related to vehicle speed, direction, or any other sensor readings.

- **Enhance Grafana Dashboard**: The Grafana dashboard can be tailored to display the additional data points collected from the GPS tracker. You can add new panels, visualizations, and filters to create a dashboard that provides valuable insights for your specific use case.

- **Integrate with External Services**: If you have specific external services or APIs you'd like to integrate with, you can modify the Python script to send data to those services. This could include data storage in cloud platforms, real-time alerts, or other notifications.

- **Utilize SD Card Storage**: Take advantage of the SD Card slot on the SIM7600G-H 4G to create a backup of the database. This ensures data redundancy and availability in various scenarios.

- **Fine-Tune GPS Accuracy**: Depending on your tracking needs, you can explore ways to improve GPS accuracy, such as fine-tuning the frequency of data collection, incorporating more advanced GPS modules, or implementing data filtering algorithms.

- **Advanced Analytics**: If you're looking to extract advanced insights from the collected GPS data, you can incorporate data analysis techniques, machine learning models, or predictive analytics to derive valuable information from the tracker's data stream.

### Advantages of AI Agent Host-Based GPS Tracker over Traditional Trackers.


The AI Agent Host-Based GPS Tracker offers numerous benefits and advantages compared to traditional GPS trackers. By leveraging advanced technology and a unique approach, this solution provides users with an enhanced tracking experience and greater control over their data. Here are some of the key advantages:

- **Privacy and Control**: The AI Agent Host-Based GPS Tracker operates without relying on third-party tracking services or external servers. This ensures that your location data remains under your control, minimizing the risk of unauthorized access or data sharing.

- **Data Ownership**: With this tracker, you own and control the data generated by the device. Unlike some trackers that might share or monetize your data in exchange for no monthly fees, the AI Agent Host-Based GPS Tracker puts data ownership back in your hands.

- **No Monthly Fees**: Similar to traditional no monthly fee trackers, our solution eliminates the need for recurring subscription costs. However, it goes beyond by offering advanced tracking capabilities without relying on external servers.

- **Customization and Integration**: Tailor the AI Agent Host-Based GPS Tracker to your specific needs. Enjoy the flexibility to customize its behavior, integrate it with other systems, and even develop additional features as required.

- **Advanced Capabilities**: Depending on the AI capabilities you implement, this tracker can provide advanced features such as intelligent route optimization, predictive maintenance, anomaly detection, and more.

- **Security**: Operating within your own environment, the tracker reduces the risk of security breaches associated with external servers. You can implement your own security measures to protect your data effectively.

- **Offline Functionality**: The GPS tracker can continue functioning even when there's no internet connectivity. It can store data locally and sync it when the connection is restored, ensuring seamless tracking under various conditions.

- **Custom Alerts and Triggers**: Set up personalized alerts and triggers based on your criteria. This high level of customization enables you to receive notifications when specific events occur.

- **Learning and Improvement**: Benefit from the AI capabilities of the tracker, which learns from historical data to enhance its functionality over time. This can result in more accurate predictions and valuable insights.

The AI Agent Host-Based GPS Tracker provides users with greater control, privacy, and customization options compared to traditional trackers. It empowers you to design a tracking solution that precisely fits your needs while maintaining ownership of your data and reducing reliance on external services.
 
### Goal

With this diverse suite of ready-to-use notebooks, users can delve into various domains without the hassle of setting up from ground zero. Especially beneficial for those starting their journey in data science, it offers a clear roadmap for experimentation.

### Contribute

Your insights are invaluable! We ardently invite the community to pitch in with their expertise to nurture and expand this suite of notebooks. Let's collaboratively enhance the capability of the AI Agent Host for all data science enthusiasts!
