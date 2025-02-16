# Weather App - A DevOps Project

This Weather App is a DevOps project that integrates continuous integration, continuous deployment, containerization, and infrastructure automation. It provides real-time weather information for various locations and is built using Python, JavaScript, HTML, and CSS. The application utilizes the OpenWeatherMap API to fetch current weather data.

## Prerequisites

- Two Linux virtual machines
- Docker installed on both virtual machines
- Jenkins installed and configured to push to your GitHub repository

## Steps to Deploy

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/Marwan-alanani/Weather-App.git
   cd Weather-App
   ```

2. **Insert Your VM Private Keys**:
   - Place your virtual machine private keys inside the `private_keys/` directory.

3. **Modify the Inventory File**:
   - Update the `inventory` file to include your virtual machines' IP addresses.

4. **Run Vagrant**:
   ```bash
   vagrant up
   ```
   - This will provision the virtual machines and set up the environment.

5. **Run Ansible Playbook**:
   ```bash
   ansible-playbook -i inventory setup.yml
   ```
   - This configures the application, installs dependencies, and deploys the weather app.

6. **Verify Docker Containers**:
   ```bash
   docker ps
   ```
   - Ensure that the application containers are running successfully.

7. **Configure Jenkins for CI/CD**:
   - Set up a Jenkins pipeline to automate the deployment.
   - Add the repository URL and credentials to Jenkins.
   - Enable GitHub webhooks to trigger Jenkins builds on code changes.

8. **Access the Application**:
   - The application should now be accessible at `http://<your-vm-ip>:5000/`.

## Contributing

Contributions are welcome! Please fork this repository and submit a pull request for any enhancements or bug fixes.

## License

This project is licensed under the MIT License.

## Acknowledgements

- [OpenWeatherMap](https://openweathermap.org/) for providing the weather data API.
- [GitHub](https://github.com/) for hosting the repository.

---

For any questions or support, please open an issue in this repository.
