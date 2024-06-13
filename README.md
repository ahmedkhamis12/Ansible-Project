# Node.js Application Deployment with Ansible

This project demonstrates how to automate the deployment of a Node.js application using Ansible. The playbook provisions a server, installs necessary dependencies, and deploys a simple Node.js application.

## Table of Contents

- [Project Overview](#project-overview)
- [Prerequisites](#prerequisites)
- [Project Structure](#project-structure)
- [Setup Instructions](#setup-instructions)
- [Usage](#usage)
- [Contributing](#contributing)
- [License](#license)

## Project Overview

The project uses Ansible to:
1. Update the package repository and cache.
2. Install Node.js and npm.
3. Deploy the Node.js application from an archive.
4. Install application dependencies using npm.
5. Start the Node.js application.
6. Verify that the application is running.

## Prerequisites

- Ansible 2.9+ installed on your local machine.
- SSH access to the target server.
- The target server should be running a Debian-based distribution (e.g., Ubuntu).
- Node.js application packaged in a `.tgz` file.

## Project Structure

.
├── ansible-playbook.yml # Main Ansible playbook
├── simple-nodejs-app/ # Directory containing the Node.js application
│ └── nodejs-app-1.0.0.tgz # Packaged Node.js application
└── README.md # This README file


## Setup Instructions

1. **Clone the repository:**

    ```bash
    git clone https://github.com/ahmedkhamis12/Ansible-Project.git
    cd your -Ansible-Project
    ```

2. **Ensure you have an Ansible inventory file:**

    Create an `hosts` file to list your target server(s). For example:
    
    ```ini
    [servers]
    3.80.227.221 ansible_user=ubuntu
    ```

3. **Check Ansible configuration:**

    Ensure your `ansible.cfg` is set up correctly, particularly with the path to your inventory file and any necessary SSH settings.

## Usage

1. **Run the playbook:**

    ```bash
    ansible-playbook -i hosts ansible-playbook.yml
    ```

2. **Verify the application is running:**

    The playbook includes a task to check if the Node.js application is running. You can also manually check by SSHing into the server and running:

    ```bash
    ps aux | grep node
    ```

## Contributing

We welcome contributions! Please fork this repository and submit pull requests.

1. Fork the repository.
2. Create a new branch (`git checkout -b feature-branch`).
3. Make your changes.
4. Commit your changes (`git commit -m 'Add some feature'`).
5. Push to the branch (`git push origin feature-branch`).
6. Open a pull request.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
