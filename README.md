# Weather App

This Weather App is a web application that provides real-time weather information for various locations. It is built using Python, JavaScript, HTML, and CSS, and utilizes the OpenWeatherMap API to fetch current weather data.

## Features

- **Real-Time Weather Data**: Retrieve up-to-date weather information for any city worldwide.
- **User-Friendly Interface**: Simple and intuitive design for easy navigation and data interpretation.

## Technologies Used

- **Frontend**: HTML, CSS, JavaScript
- **Backend**: Python
- **API**: OpenWeatherMap
- **Containerization**: Docker
- **Automation**: Jenkins
- **Virtualization**: Vagrant

## Getting Started

To run this project locally, follow these steps:

### Prerequisites

- Python installed on your machine
- Docker installed
- Vagrant installed
- Jenkins installed
- An API key from [OpenWeatherMap](https://openweathermap.org/api)

### Installation

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/Marwan-alanani/Weather-App.git
   cd Weather-App
   ```

2. **Set Up Virtual Environment**:
   ```bash
   python -m venv env
   source env/bin/activate  # On Windows, use `env\Scripts\activate`
   ```

3. **Install Dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

4. **Configure API Key**:
   Create a file named `.env` in the project root directory and add your OpenWeatherMap API key:
   ```
   API_KEY=your_openweathermap_api_key
   ```

5. **Run the Application**:
   ```bash
   python app.py
   ```
   The application should now be running on `http://localhost:5000/`.

## Docker Deployment

To deploy the application using Docker:

1. **Build the Docker Image**:
   ```bash
   docker build -t weather-app .
   ```

2. **Run the Docker Container**:
   ```bash
   docker run -d -p 5000:5000 --env-file .env weather-app
   ```
   The application will be accessible at `http://localhost:5000/`.

## Vagrant Deployment

To set up the application using Vagrant:

1. **Initialize and Start Vagrant**:
   ```bash
   vagrant up
   ```
   This command will set up a virtual machine and deploy the application.

2. **Access the Application**:
   Once the setup is complete, the application will be running, and you can access it as directed in the Vagrant output.

## Jenkins Integration

A `Jenkinsfile` is included for CI/CD automation. To set up Jenkins integration:

1. **Install Jenkins**: Follow the official [Jenkins installation guide](https://www.jenkins.io/doc/book/installing/).
2. **Create a New Pipeline**: In Jenkins, create a new pipeline and configure it to use the repository containing this project.
3. **Configure Credentials**: Ensure that Jenkins has access to any necessary credentials, including the OpenWeatherMap API key.
4. **Build the Pipeline**: Run the pipeline to automate the build and deployment process.

## Contributing

Contributions are welcome! Please fork this repository and submit a pull request for any enhancements or bug fixes.

## License

This project is licensed under the MIT License.

## Acknowledgements

- [OpenWeatherMap](https://openweathermap.org/) for providing the weather data API.
- [GitHub](https://github.com/) for hosting the repository.

---

For any questions or support, please open an issue in this repository.
