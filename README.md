# Weather App - A DevOps Project

This Weather App is a DevOps project that integrates continuous integration, continuous deployment, containerization, and infrastructure automation. It provides real-time weather information for various locations and is built using Python, JavaScript, HTML, and CSS. The application utilizes the OpenWeatherMap API to fetch current weather data.

## Prerequisites

- Two Linux virtual machines
- Docker installed on both virtual machines
- Jenkins installed and configured to push to your GitHub repository
- Ansible installed

## Steps to Deploy

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/Marwan-alanani/Weather-App.git
   cd Weather-App
   ```

2. **Insert Your VM Private Keys**:
   - Place your virtual machine private keys inside the `Weather-App/private_keys/` directory.

3. **Modify the Inventory File**:
   - Update the `inventory` file to include your virtual machines' IP addresses.

4. **Run Vagrant**:
   ```bash
   vagrant up
   ```
   - This will provision the virtual machines and set up the environment.

5. **Confirm Inventory Configuration**:
   ```bash
   ansible -i inventory all -m ping
   ```
   - This ensures Ansible can communicate with the virtual machines.

6. **Configure Jenkins for GitHub Integration**:
   - Add an SSH key to Jenkins so it can push to your GitHub repository.

7. **Configure Jenkins for DockerHub Integration**:
   - Grant Jenkins the necessary permissions to push images to your DockerHub repository.

8. **Modify Ansible Playbook**:
   - Update the Ansible playbook to push the application image to your DockerHub repository.

9. **Run the Jenkins Pipeline**:
   - Execute the Jenkinsfile to automate the build and deployment process.

## Contributing

Contributions are welcome! Please fork this repository and submit a pull request for any enhancements or bug fixes.

## License

This project is licensed under the MIT License.

## Acknowledgements

- [OpenWeatherMap](https://openweathermap.org/) for providing the weather data API.
- [GitHub](https://github.com/) for hosting the repository.

---

For any questions or support, please open an issue in this repository.
