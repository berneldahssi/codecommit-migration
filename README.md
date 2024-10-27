# 🚀 CodeCommit to GitHub Migration with Ansible

## 📝 Overview

This repository contains Ansible playbooks to automate the migration of private AWS CodeCommit repositories to GitHub as private repositories. With AWS CodeCommit deprecating support, this solution provides a reliable, streamlined approach to transferring repositories with minimal manual work. The playbooks are scalable and flexible, allowing migrations across multiple repositories and accounts.

## 🌟 Key Features

- 🔄 **Automated Migration**: Transfers repositories from CodeCommit to GitHub, preserving history and commit integrity.
- 🔐 **Private Repository Configuration**: Migrates repositories as private GitHub repositories to maintain controlled access.
- ⚙️ **Configurable**: Customize GitHub organization, access permissions, and repository settings.
- 📋 **Detailed Logging**: Logs migration status and errors to ensure traceability and aid in troubleshooting.
- 📈 **Scalable Solution**: Supports batch migration of multiple repositories, ideal for medium to large-scale migrations.

## 📋 Prerequisites

- 🖥️ **AWS CLI** configured with sufficient permissions to access CodeCommit repositories.
- 🔑 **GitHub Personal Access Token** with `repo` permissions to create private repositories.
- 🐍 **Ansible** installed on your local environment.
- 🧩 **Python** installed and compatible with Ansible requirements.

## ⚙️ Setup

1. Clone this repository:  
   ```bash
   git clone https://github.com/yourusername/codecommit-to-github-migration-ansible.git
   cd codecommit-to-github-migration-ansible
   ```

2. Configure the required variables in the `group_vars/all.yml` file:  
   - `aws_region`: AWS region for CodeCommit.
   - `github_org`: GitHub organization or username.
   - `github_token`: GitHub personal access token.

3. Run the Ansible playbook:  
   ```bash
   ansible-playbook migrate_codecommit_to_github.yml
   ```

## 📂 Playbook Structure

- **migrate_codecommit_to_github.yml**: Main playbook for handling the migration.
- **roles/**:
  - `codecommit_repos`: Fetches CodeCommit repositories for migration.
  - `github_setup`: Creates equivalent private repositories in GitHub.
  - `migration_tasks`: Uses Git commands to mirror repositories from CodeCommit to GitHub.

## 🚀 Usage

These playbooks use Git to clone repositories from CodeCommit and push them to GitHub, ensuring branches, tags, and commit history are preserved. To migrate specific repositories, you can use the `--limit` flag to specify which repositories or accounts to migrate.

## 📜 License

This project is licensed under the MIT License.
