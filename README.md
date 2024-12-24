# Jekyll Test Repository

A test repository for creating GitHub Pages using Jekyll and automated deployment with GitHub Actions.

## 🚀 Features

- Static site generation with Jekyll
- Automated deployment via GitHub Actions on PR merges to main
- GitHub Pages demonstration

## 📦 Repository Structure

```
.
├── .github/
│   └── workflows/
│       └── deploy.yml
├── _posts
├── _config.yml
├── index.md
└── README.md
```

## 🔧 Setup & Deployment

1. Repository automatically deploys when pushing or merging PRs to `main` branch
2. Deployment process is handled through GitHub Actions (see `.github/workflows/deploy.yml`)
3. Website is accessible at: `${{ github.event.repository.html_url }}`

## 📝 Workflow

1. Create new branch from `main`
2. Make changes
3. Create Pull Request to `main`
4. After merging, GitHub Actions will automatically build and deploy

## 🤝 Contributing

This is a test repository, not accepting contributions.

## 📄 License

[MIT License](LICENSE)

## 👤 Author

GitHub: [@${{ github.repository_owner }}](${{ github.repository_owner_url }})

## ⚙️ Development

### Prerequisites
- Git

### Local Setup
```bash
# Clone the repository
git clone ${{ github.repositoryUrl }}

# Navigate to repository folder
cd ${{ github.event.repository.name }}
```

### Building and Testing
- Push changes to your branch
- Create a PR to main
- GitHub Actions will automatically build and deploy when merged

## 🔍 Status

[![Deploy static content to Pages](${{ github.repository }}/actions/workflows/deploy.yml/badge.svg)](${{ github.repository }}/actions/workflows/deploy.yml)
