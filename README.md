# Ansible DevOps Automation: Docker, Docker Compose & Nginx

## 📌 Project Overview
This project automates the installation of Docker, Docker Compose, and Nginx using Ansible. It streamlines the setup process for deploying containerized applications on a local Ubuntu system.

## 📂 Project Structure

```
Devops_A4/
│
├── README.md
├── playbook.yml
├── roles/
│   ├── docker/
│   │   └── tasks/
│   │       └── main.yml
│   ├── docker_compose/
│   │   └── tasks/
│   │       └── main.yml
│   └── nginx/
│       └── tasks/
│           └── main.yml
└── Devops_A4.jpeg
```

## 🌟 Features

- Automated installation of Docker and Docker Compose
- Deployment of Nginx for reverse proxy
- Lightweight and scalable playbook

## 🚀 Prerequisites

- Ansible installed on your system
- Ubuntu operating system

## 🛠️ Installation

1. Clone the repository:

```bash
git clone https://github.com/hasan914/ansible-devops.git
```

2. Navigate to the project directory:

```bash
cd ansible-devops
```

3. Run the Ansible playbook:

```bash
ansible-playbook playbook.yml --ask-become-pass
```

## ✅ Tasks Included

- Install Docker and Docker Compose
- Add Docker GPG key and repository
- Install and configure Nginx
- Ensure services are running

## 📜 Playbook Details

- **Docker Role**: Handles Docker installation and configuration
- **Docker Compose Role**: Downloads and sets up Docker Compose
- **Nginx Role**: Installs and ensures Nginx is running

## 🚀 Technologies Used

- Ansible
- Docker
- Docker Compose
- Nginx
- Ubuntu Linux

## 🌐 Access the Application

Once the playbook runs successfully, Nginx will be accessible at:

```bash
http://localhost
```

## 🐳 Docker Version

```bash
docker --version
```

## 🎯 Future Enhancements

- CI/CD pipeline integration
- SSL certificate setup
- Automated security patching

## 🤝 Contribution

Contributions are welcome! Feel free to fork the repository and submit pull requests.


## 🌟 Author

Created with ❤️ by **Hasan Javed**

- LinkedIn: [hasanjaved667](https://www.linkedin.com/in/hasanjaved667/)
- GitHub: [hasan914](https://github.com/hasan914)

---

## 🛑 License

This project is licensed under the **MIT License**.

