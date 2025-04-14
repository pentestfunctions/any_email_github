# 🔄 Any Email GitHub 🔄

This repository demonstrates how to use any email address or username for GitHub commits. 

> **Real Example**: Compare these two URLs:
> - Normal commit view: [https://github.com/pentestfunctions/pentestfunctions/commit/15bff73c63bd954769c622da9570fba53a4b0749](https://github.com/pentestfunctions/pentestfunctions/commit/15bff73c63bd954769c622da9570fba53a4b0749)
> - Patch endpoint: [https://github.com/pentestfunctions/pentestfunctions/commit/15bff73c63bd954769c622da9570fba53a4b0749.patch](https://github.com/pentestfunctions/pentestfunctions/commit/15bff73c63bd954769c622da9570fba53a4b0749.patch)
>
> The patch endpoint reveals the actual email address used in the commit, showing how this technique works in practice.

---

## 🎯 Purpose

This technique can be useful for:
- 🧪 Testing different commit signatures
- 🔀 Separating work/personal commits with different identities
- 🎭 Creating demo repositories with fictional contributor identities
- 🔒 Pentesting/security research purposes

> It can also be used to fool employers into who you have worked with as well as potential agencies/governments you have had an email for when users are trying to OSINT you.
---

## 💡 How It Works

Git allows you to set your name and email address locally, which are then used for commit signatures. GitHub displays these values in the commit history without verification.

---

## 📋 Basic Usage

### ⚙️ Setting Any Email/Username for a Single Repository

```bash
# Clone the repository
git clone https://github.com/yourusername/your-repository.git

# Navigate to repository
cd your-repository

# Set custom username and email for this repository only
git config user.name "Any Name You Want"
git config user.email "any.email@example.com"

# Create or modify a file
echo "Test content" > testfile.txt

# Add and commit the file
git add testfile.txt
git commit -m "Commit with custom identity"

# Push to GitHub (requires authentication with YOUR token/credentials)
git push origin main
```

### 🌐 Setting Global Email/Username (affects all repositories)

```bash
# Set global username and email
git config --global user.name "Any Name You Want"
git config --global user.email "any.email@example.com"
```

---

## ⚠️ Important Notes

1. **Authentication**: While you can use any email/username for commits, you still need valid GitHub authentication to push changes.

2. **Verified Commits**: This approach won't create verified commits (with the green "Verified" badge). For that, you'd need GPG signing with a key associated with the email address.

3. **Email Privacy**: If you use an actual email address, it will be publicly visible in Git history.

4. **GitHub Contributions**: Commits may not show up on your GitHub contribution graph if the email doesn't match any verified email in your GitHub account.

5. **Commit Patch Endpoint**: The `.patch` endpoint on GitHub commit URLs (e.g., `https://github.com/user/repo/commit/hash.patch`) exposes the raw commit data including email addresses. This is important to be aware of as it can reveal information not immediately visible in the GitHub UI.

---

## 🧩 Example Patterns

You can use various patterns for your custom emails:

```bash
# Organization identity
git config user.name "Company Name"
git config user.email "dev@company.com"

# Domain-specific identity
git config user.name "Security Tester"
git config user.email "tester@security.gov"

# Project-specific identity
git config user.name "Project X Developer"
git config user.email "dev@projectx.com"
```

---

## 🔍 Viewing Your Current Git Configuration

```bash
# View repository-specific settings
git config --list --local

# View all settings (including global)
git config --list
```

---

## 🤔 Practical Use Cases

- **Multiple Organizations**: Maintain separate identities when contributing to different organizations
- **Client Work**: Use client-specific identities for different projects
- **Testing**: Test how commit signatures appear in different contexts
- **Education**: Demonstrate Git identity concepts in educational environments

### 🧪 Advanced Use Cases

- **Portfolio Enhancement**: Create commits that appear to be from prestigious organizations or domains (e.g., `dev@famous-company.com`)
- **Reputation Building**: Generate a commit history that suggests collaboration with well-known developers or organizations
- **Security Awareness**: Demonstrate to employers or clients how easy it is to spoof commit identities, raising awareness about the importance of verified commits
- **Social Engineering Testing**: Test if people verify commit authors or blindly trust what's displayed in the GitHub UI

> ⚠️ **Note**: These advanced techniques should be used responsibly and ethically, primarily for educational purposes. Misrepresentation may violate GitHub's terms of service and could have professional consequences.

---

## 📝 Step-by-Step Example

> 💡 **Pro Tip**: Understanding the `.patch` endpoint can help you verify the true origin of commits. Add `.patch` to any commit URL to see the raw email address used, which can reveal whether commits are genuine or spoofed.
>
> **Real Example**: Compare these two URLs:
> - Normal commit view: [https://github.com/pentestfunctions/pentestfunctions/commit/15bff73c63bd954769c622da9570fba53a4b0749](https://github.com/pentestfunctions/pentestfunctions/commit/15bff73c63bd954769c622da9570fba53a4b0749)
> - Patch endpoint: [https://github.com/pentestfunctions/pentestfunctions/commit/15bff73c63bd954769c622da9570fba53a4b0749.patch](https://github.com/pentestfunctions/pentestfunctions/commit/15bff73c63bd954769c622da9570fba53a4b0749.patch)
>
> The patch endpoint reveals the actual email address used in the commit, showing how this technique works in practice.

Let's walk through a complete example:

1. **Create a new repository**
   ```bash
   mkdir custom-identity-test
   cd custom-identity-test
   git init
   ```

2. **Set a custom identity**
   ```bash
   git config user.name "Test User"
   git config user.email "test@example.org"
   ```

3. **Create and commit a file**
   ```bash
   echo "# Test Repository" > README.md
   git add README.md
   git commit -m "Initial commit"
   ```

4. **Connect to GitHub and push**
   ```bash
   git remote add origin https://github.com/yourusername/custom-identity-test.git
   git push -u origin main
   ```

5. **Check the commit on GitHub**
   - Go to your repository on GitHub
   - Click on the commit history
   - You'll see the commit attributed to "Test User" with the email "test@example.org"

---

## ⚖️ Ethical Considerations

Please use this capability responsibly:
- 🚫 Don't impersonate real individuals or organizations with intent to deceive
- 📜 Be aware of your organization's policies regarding commit identity
- 🔬 Consider using this for legitimate testing purposes only

---
