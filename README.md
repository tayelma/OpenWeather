# **Weather Dashboard**
A Python-based application that fetches real-time weather data for selected cities using the OpenWeather API, visualizes the weather information, and stores the data in an AWS S3 bucket in JSON format.
## **Features**
- Fetches current weather data including temperature, humidity, and weather description for selected cities.
- Automatically creates an S3 bucket (if not exists) to store weather data in JSON format.
- **Visualization Feature(add-on)**: Displays the fetched weather data as charts/graphs (e.g., temperature comparison).



## **Technologies Used**
- **Python 3.x**: Core application language.
- **boto3**: AWS SDK for Python to interact with Amazon S3.
- **requests**: For making HTTP requests to the OpenWeather API.
- **python-dotenv**: For securely loading environment variables.
- **matplotlib**: For visualizing weather data through charts/graphs.
- **AWS S3**: Cloud storage for weather data.

## **Project Structure**


├── weather_dashboard.py      # Main Python script for the application

├── requirements.txt          # Python dependencies file

├── .env                      # Environment variables file (not committed to source control)

└── README.md                 # Documentation for the project


## **Setup & Installation**
Follow these steps to set up and run the project:
### 1. Clone the Project

>git clone _https://github.com/tayelma/OpenWeather.git_

>cd <repository-folder>

### 2. Create a Virtual Environment
It’s recommended to use a virtual environment to manage dependencies:

`python -m venv _your_virtual_environment_name_ `

`source _your_virtual_environment_name_\Scripts\activate`

### 3. Install Dependencies

Install the required Python libraries using `pip`:
Here is the list of Python libraries used in your project, based on the script and explanation provided. This can be included in your `requirements.txt` file:
### **Python Libraries**
1. `boto3`: For interacting with AWS services (like S3).
2. `requests`: For making HTTP requests to the OpenWeather API.
3. `python-dotenv`: For securely loading environment variables from a `.env` file.
4. `matplotlib`: For visualizing weather data as charts or graphs (optional, based on the visualization feature).
5. `urllib3`: (Optional dependency of `boto3` and `requests`, typically included automatically).

`pip install -r requirements.txt`

### Dependencies in my requirements.txt:

>boto3==1.26.137
    python-dotenv==1.0.0
    requests==2.28.2
    matplotlib==3.10.0
>    pandas==2.2.3

###  4. Configure Environment Variables
1. Create a `.env` file in the project directory.
2. Add the following keys and values to your `.env` file:

>OPENWEATHER_API_KEY=your_openweather_api_key_here
AWS_BUCKET_NAME=your_s3_bucket_name_here
> 
Replace the placeholders (`your_openweather_api_key_here`, etc.) with your actual API key and AWS credentials.

 **Note**: Never share your `.env` file or commit it to version control (e.g., GitHub).

###  5. Configure AWS Environment
Set up your AWS environement with `aws configure` and input your required `access key, secret access key, region output format.
`

## **Running the Application**
Run the script from your terminal:

`python weather_dashboard.py`

The application will:
1. Check if the specified S3 bucket exists, and create it if not.
2. Fetch weather data for the selected cities (hardcoded in the script, e.g., Accra, Lagos, Johannesburg).
3. Visualize the weather data in the form of charts/graphs (e.g., comparing temperatures across different cities).
4. Print the weather data to the console.
5. Save the weather data to the S3 bucket in JSON format, with a timestamp.

## **Visualization Feature (add-on):**

As an additional (non-challenge) feature, I included the feature to visualise the weather data stored as json in s3.
Using the `matplotlib` library, the code in `interactive-visualisation.py` displays:
`the json data in a tabular form`
`allows you to select the metric to visualize`
`toggle between the your chart type preference (currently only bar chart and line graph are available)`

To view the above run ` streamlit run interactive-visualisation.py `, this should open your visualisation in your default browser automatically. If not you can click on the urls that will be provided in the output to display the visualisation.

![image](https://github.com/user-attachments/assets/c52f624b-61c6-4871-80d1-02e31d3a5588)

![image](https://github.com/user-attachments/assets/e187ddd2-bd11-43d4-9a34-f297f1546db4)





