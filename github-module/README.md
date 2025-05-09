# Git and GitHub for Developers

## Table of Contents
- [Part I: Git/GitHub Basics](#part-i-gitgithub-basics)
  - [Introduction to Git and Version Control](#1-introduction-to-git-and-version-control)
  - [Introduction to GitHub](#2-introduction-to-github)
  - [How Git and GitHub Work Together](#3-how-git-and-github-work-together)
- [Getting Started with Git and GitHub](#2-getting-started-with-git-and-github)
  - [Git Installation](#1-git-installation)
  - [Creating a GitHub Account](#2-creating-a-github-account)
- [Git/GitHub Basic Workflow](#3-gitgithub-basic-workflow)
  - [Creating a Repository](#1-creating-a-repository)
  - [Setting up the Local Repository](#2-setting-up-the-local-repository-for-the-first-time)
  - [Your First Push](#3-your-first-push)
- [Key Parts of a Repository](#4-key-parts-of-a-repository)
  - [README File](#1-readme-file)
  - [.gitignore](#2-gitignore)
  - [Code Folders](#3-code-folders)
  - [.gitkeep](#4-gitkeep)
- [Collaborating with Git/GitHub](#5-collaborating-with-gitgithub)
  - [How to Clone a Repository](#1-how-to-clone-a-repository)
  - [How to Push Changes](#2-how-to-push-changes-to-an-unlocked-branch)
  - [Pulling Other People's Changes](#3-pulling-other-peoples-changes)
  - [Resolving Merge Conflicts](#4-resolving-merge-conflicts)
- [Part II: Project Management with Git](#part-ii-project-management-with-git)
  - [GitHub Project Tools Overview](#1-github-project-tools-overview)
    - [Planning Board](#planning-board)
    - [Roadmaps](#roadmaps)
    - [Issues](#issues)
    - [Development Branches](#development-branches)
    - [Pull Requests](#pull-requests)
    - [Reviewers and Merges](#reviewers-and-merges)
    - [Closing Issues, PRs, and Branches](#closing-issues-prs-and-branches)
  - [GitHub Project Walkthrough](#2-github-project-walkthrough)

## Part I: Git/GitHub Basics

### 1. Introduction to Git and Version Control

#### What is Version Control?
Version control is a system that records changes to files over time so you can recall specific versions later. For developers, this means tracking changes to your code, documentation, and project resources to maintain a complete history of your development process. As noted in "Beginning Git and GitHub" (Tsitoara, 2024, p.3), version control helps you effectively manage multiple versions of a project.

#### Why Use Version Control?
- **History Tracking**: Track who changed what in your code, when, and why
- **Collaboration**: Work with team members on the same codebase without overwriting each other's work
- **Backup**: Maintain a complete history of your development
- **Experimentation**: Create branches to test new implementations without affecting production code
- **Documentation**: Maintain a record of all changes to support audit requirements

#### What is Git?
Git is a distributed version control system designed for speed, data integrity, and support for distributed, non-linear workflows. Unlike traditional centralized version control systems, Git gives each developer a local copy of the entire development history. As detailed in "Beginning Git and GitHub" (Tsitoara, 2024, p.11), Git is faster than older VCS systems because it takes snapshots rather than storing differences between versions.

### 2. Introduction to GitHub

GitHub is a cloud-based hosting service that lets you manage Git repositories. For developers, GitHub provides:

- A central place to store repositories
- Collaboration tools for team development
- Issue tracking for bug fixes and feature requests
- Project management tools to organize development
- Documentation hosting for code standards and practices

"Beginning Git and GitHub" (Tsitoara, 2024, p.101) describes GitHub as "a development platform inspired by the way you work," providing tools that go beyond simple code hosting to enable complete project management.

### 3. How Git and GitHub Work Together

- **Local Development**: Write and test code on your local machine
- **Commit Changes**: Save snapshots of your code locally
- **Push to GitHub**: Share your commits with the team by pushing to GitHub
- **Pull from GitHub**: Get the latest code updates from your team
- **GitHub Features**: Use GitHub's tools for code reviews, issue tracking, and project management

## 2. Getting Started with Git and GitHub

### 1. Git Installation

#### Windows Installation
1. Download Git from [git-scm.com](https://git-scm.com/download/win)
2. Run the installer, accepting the default settings
3. Open Git Bash to verify the installation:
   ```bash
   git --version
   ```

#### macOS Installation
1. Install via Homebrew (recommended):
   ```bash
   brew install git
   ```
2. Verify installation:
   ```bash
   git --version
   ```

#### Linux Installation
1. For Debian/Ubuntu:
   ```bash
   sudo apt-get update
   sudo apt-get install git
   ```
2. For Red Hat/Fedora:
   ```bash
   sudo dnf install git
   ```
3. Verify installation:
   ```bash
   git --version
   ```

#### Git Configuration
Set up your identity (used for commit history):
```bash
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```

"Beginning Git and GitHub" (Tsitoara, 2024, p.37) emphasizes the importance of this configuration step as it identifies you as the author of your commits.

### 2. Creating a GitHub Account

1. Visit [github.com](https://github.com) and click "Sign up"
2. Follow the prompts to create your account
3. Choose a free plan for individual use
4. Verify your email address
5. Set up two-factor authentication (recommended for security)

## 3. Git/GitHub Basic Workflow

### 1. Creating a Repository

#### Creating a Repository on GitHub
1. Log in to GitHub
2. Click the "+" icon in the upper right corner and select "New repository"
3. Name your repository (e.g., "oracle-sql-scripts")
4. Add a description: "A collection of Oracle SQL scripts for data analysis"
5. Choose "Public" or "Private" visibility
6. Check "Add a README file"
7. Add a .gitignore file and select "Oracle" template
8. Choose a license if needed
9. Click "Create repository"

### 2. Setting up the Local Repository for the First Time

#### Cloning the Repository
1. On GitHub, navigate to your new repository
2. Click the "Code" button and copy the HTTPS or SSH URL
3. Open your terminal or Git Bash
4. Navigate to where you want to store the repository:
   ```bash
   cd Documents/Projects
   ```
5. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/oracle-sql-scripts.git
   ```
6. Navigate into the repository:
   ```bash
   cd oracle-sql-scripts
   ```

"Beginning Git and GitHub" (Tsitoara, 2024, p.43) explains that cloning creates a complete copy of the repository, including its entire history.

### 3. Your First Push

#### Creating Your First SQL Script
1. Create a new file called `employee_queries.sql`:
   ```bash
   touch employee_queries.sql
   ```
2. Open the file in your preferred editor and add some SQL:
   ```sql
   -- Basic employee queries
   -- Created: [Current date]
   
   -- Query to get all employees
   SELECT employee_id, first_name, last_name, email, job_id
   FROM employees
   ORDER BY employee_id;
   
   -- Query to get employees by department
   SELECT e.employee_id, e.first_name, e.last_name, d.department_name
   FROM employees e
   JOIN departments d ON e.department_id = d.department_id
   ORDER BY d.department_name, e.last_name;
   ```

#### Committing and Pushing Changes
1. Check the status of your repository:
   ```bash
   git status
   ```
2. Add your new file to staging:
   ```bash
   git add employee_queries.sql
   ```
3. Commit your changes:
   ```bash
   git commit -m "Add basic employee queries"
   ```
4. Push your changes to GitHub:
   ```bash
   git push origin main
   ```
5. Visit your GitHub repository to see the changes

"Beginning Git and GitHub" (Tsitoara, 2024, p.86) emphasizes the importance of writing clear commit messages that explain why the changes were made.

## 4. Key Parts of a Repository

### 1. README File

The README.md file is the landing page for your repository. For repositories, it should include:

- Project description
- Compatibility information
- Setup instructions
- Usage examples
- Directory structure explanation

Example README.md for Oracle SQL repository:
```markdown
# Oracle SQL Scripts Collection

A collection of Oracle SQL scripts for data analysis, reporting, and database maintenance.

## Database Compatibility

These scripts are compatible with Oracle Database 12c and later.

## Directory Structure

- `queries/`: Common SQL queries for data analysis
- `reports/`: SQL scripts that generate business reports
- `admin/`: Database administration scripts
- `functions/`: User-defined functions and procedures

## Usage

To use these scripts:

1. Connect to your Oracle database using SQL*Plus or Oracle SQL Developer
2. Open the desired script
3. Modify any parameters as needed (look for comments with "PARAM:")
4. Execute the script

## Contributing

Please see CONTRIBUTING.md for details on our code of conduct and the process for submitting pull requests.
```

### 2. .gitignore

The .gitignore file specifies files that Git should ignore. For Oracle SQL development:

```
# Oracle SQL Developer files
*.sql~
*.bak
*.~sql

# Oracle Data Modeler files
*.local
*.log
*.cdb
*.hdb
*.jewb
*.jdb

# Environment-specific files
*.env
connection.properties
credentials.sql

# Operating system files
.DS_Store
Thumbs.db

# Compiled PL/SQL output
*.plb

# Temporary files
temp/
tmp/
*.tmp
```

"Beginning Git and GitHub" (Tsitoara, 2024, p.55) explains that the .gitignore file helps keep your repository clean by excluding files that shouldn't be tracked.

### 3. Code Folders

Organize your scripts logically:

```
oracle-sql-scripts/
├── queries/
│   ├── employees/
│   │   ├── employee_search.sql
│   │   └── employee_reports.sql
│   └── finance/
│       ├── revenue_analysis.sql
│       └── expense_reports.sql
├── admin/
│   ├── maintenance/
│   │   ├── rebuild_indexes.sql
│   │   └── purge_audit_logs.sql
│   └── security/
│       ├── user_management.sql
│       └── role_assignments.sql
├── functions/
│   ├── date_functions.sql
│   └── string_functions.sql
└── procedures/
    ├── data_import.sql
    └── report_generation.sql
```

### 4. .gitkeep

Git doesn't track empty directories. To include empty directories in your repository, add a `.gitkeep` file:

```bash
mkdir -p reports/monthly
touch reports/monthly/.gitkeep
```

## 5. Collaborating with Git/GitHub

### 1. How to Clone a Repository

Cloning creates a local copy of a repository:

```bash
git clone https://github.com/team-name/oracle-sql-scripts.git
cd oracle-sql-scripts
```

For private repositories, you'll need to authenticate with GitHub.

### 2. How to Push Changes (to an Unlocked Branch)

After making changes to your code:

```bash
# Check status
git status

# Add all changed SQL files
git add *.sql

# Or add specific files
git add queries/sales/monthly_revenue.sql

# Commit with a descriptive message
git commit -m "Add monthly revenue query with department breakdown"

# Push to GitHub
git push origin main
```

### 3. Pulling Other People's Changes

Before starting work each day, pull the latest changes:

```bash
git pull origin main
```

This ensures you have the latest code and avoids conflicts.

### 4. Resolving Merge Conflicts

When multiple people modify the same file, conflicts can occur. For example, if two developers modify the same query:

1. When you pull, Git will show a conflict:
   ```bash
   git pull origin main
   # CONFLICT: Merge conflict in queries/sales/revenue_report.sql
   ```

2. Open the conflicted file in your editor. You'll see:
   ```sql
   -- Revenue report query
   SELECT 
   <<<<<<< HEAD
     department_id, 
     SUM(revenue) as total_revenue
     FROM sales
     GROUP BY department_id
   =======
     department_id, 
     product_category,
     SUM(revenue) as total_revenue
     FROM sales
     GROUP BY department_id, product_category
   >>>>>>> 5ab1c45... Add product category breakdown
   ```

3. Manually resolve the conflict by deciding which changes to keep:
   ```sql
   -- Revenue report query
   SELECT 
     department_id, 
     product_category,
     SUM(revenue) as total_revenue
     FROM sales
     GROUP BY department_id, product_category
   ```

4. Mark the conflict as resolved:
   ```bash
   git add queries/sales/revenue_report.sql
   ```

5. Complete the merge:
   ```bash
   git commit -m "Resolve conflict in revenue report query"
   ```

6. Push the merged changes:
   ```bash
   git push origin main
   ```

"Beginning Git and GitHub" (Tsitoara, 2024, p.219) explains the process of resolving merge conflicts, noting that this is a common occurrence in collaborative development.

## Part II: Project Management with Git

### 1. GitHub Project Tools Overview

#### Planning Board

GitHub Projects provides a Kanban-style board for planning work:

- **To Do**: Code that needs to be created or modified
- **In Progress**: Code currently being worked on
- **Review**: Code awaiting peer review
- **Done**: Completed work

Example project board items:
- "Create customer segmentation query"
- "Optimize slow-running inventory report"
- "Add index recommendations to admin scripts"

#### Roadmaps

GitHub offers timeline views for planning:
- Sprint planning for development
- Release planning for changes
- Milestone tracking for project delivery

#### Issues

Issues track specific tasks, bugs, or feature requests:

Example issue:
```
Title: Optimize customer order history query

Description:
The query in `queries/customers/order_history.sql` is taking too long to execute for customers with 1000+ orders.

Acceptance Criteria:
- Query should execute in under 3 seconds for customers with 10,000+ orders
- Maintain all current output columns and formatting
- Add execution plan analysis as a comment in the script

Related files:
- queries/customers/order_history.sql
```

"Beginning Git and GitHub" (Tsitoara, 2024, p.125) describes issues as a way to track and plan all the tasks needed in a project.

#### Development Branches

Create branches for new features or bug fixes:

```bash
# For a new feature
git checkout -b feature/add-sales-forecast-query

# For a bug fix
git checkout -b fix/optimize-inventory-query

# For general improvements
git checkout -b improve/refactor-common-table-expressions
```

#### Pull Requests

Once you've completed your work in a branch:

1. Push your branch to GitHub:
   ```bash
   git push origin feature/add-sales-forecast-query
   ```

2. Create a pull request on GitHub:
   - Navigate to your repository
   - Click "Pull requests" > "New pull request"
   - Select your branch as the "compare" branch
   - Add a title and description
   - Link related issues
   - Add reviewers
   - Submit the pull request

#### Reviewers and Merges

For code review:
- Reviewers check logic, performance, and standards
- Comments can be added to specific lines
- Suggestions can be made within the interface
- Changes can be requested before merging

After approval:
1. Merge the pull request into the main branch
2. Delete the feature branch

#### Closing Issues, PRs, and Branches

Use keywords in commit messages to automate workflow:
- "Fixes #42" - Closes issue #42 when the PR is merged
- "Closes #57" - Closes issue #57 when the PR is merged
- "Resolves #123" - Resolves issue #123 when the PR is merged

After merging, delete feature branches to keep the repository clean:
```bash
git branch -d feature/add-sales-forecast-query
git push origin --delete feature/add-sales-forecast-query
```

"Beginning Git and GitHub" (Tsitoara, 2024, p.144) explains how to use keywords in commit messages to automatically close issues.

### 2. GitHub Project Walkthrough

Let's walk through a complete workflow for a development task:

#### 1. Create an Issue

Create a new issue in GitHub:
- Title: "Add quarterly sales analysis query"
- Description: "Create a new SQL query that analyzes quarterly sales data by region and product category. The query should include year-over-year comparison."
- Labels: "enhancement", "reporting"
- Milestone: "Q2 Reporting Enhancement"

#### 2. Create a Branch

```bash
# Pull the latest changes
git pull origin main

# Create a new branch for the feature
git checkout -b feature/quarterly-sales-analysis
```

#### 3. Develop the SQL Script

Create a new file at `queries/sales/quarterly_analysis.sql`:

```sql
-- Quarterly Sales Analysis
-- Created: 2023-05-10
-- Purpose: Analyze quarterly sales with year-over-year comparison

-- Parameters:
-- YEAR_START: Starting year for analysis (default: current year - 1)
-- YEAR_END: Ending year for analysis (default: current year)

-- Define quarters as common table expression
WITH quarters AS (
  SELECT 
    EXTRACT(YEAR FROM order_date) AS year,
    TO_CHAR(order_date, 'Q') AS quarter,
    SUM(order_amount) AS total_sales,
    region_id,
    product_category_id
  FROM 
    orders o
    JOIN order_items oi ON o.order_id = oi.order_id
    JOIN products p ON oi.product_id = p.product_id
  WHERE 
    EXTRACT(YEAR FROM order_date) BETWEEN :YEAR_START AND :YEAR_END
  GROUP BY 
    EXTRACT(YEAR FROM order_date),
    TO_CHAR(order_date, 'Q'),
    region_id,
    product_category_id
),

-- Previous year sales for comparison
prev_year AS (
  SELECT
    year + 1 AS year,
    quarter,
    region_id,
    product_category_id,
    total_sales AS prev_year_sales
  FROM
    quarters
)

-- Main query with year-over-year comparison
SELECT
  q.year,
  q.quarter,
  r.region_name,
  pc.category_name,
  q.total_sales,
  py.prev_year_sales,
  CASE 
    WHEN py.prev_year_sales IS NULL THEN NULL
    WHEN py.prev_year_sales = 0 THEN NULL
    ELSE ROUND((q.total_sales - py.prev_year_sales) / py.prev_year_sales * 100, 2)
  END AS yoy_percent_change
FROM
  quarters q
  JOIN regions r ON q.region_id = r.region_id
  JOIN product_categories pc ON q.product_category_id = pc.category_id
  LEFT JOIN prev_year py ON q.year = py.year 
                         AND q.quarter = py.quarter
                         AND q.region_id = py.region_id
                         AND q.product_category_id = py.product_category_id
ORDER BY
  q.year,
  q.quarter,
  r.region_name,
  pc.category_name;
```

#### 4. Commit and Push Changes

```bash
# Add the new file
git add queries/sales/quarterly_analysis.sql

# Commit with a message referencing the issue
git commit -m "Add quarterly sales analysis query with YoY comparison. Fixes #42"

# Push to GitHub
git push origin feature/quarterly-sales-analysis
```

#### 5. Create a Pull Request

On GitHub:
1. Go to your repository
2. Click "Pull requests" > "New pull request"
3. Set the base to "main" and compare to "feature/quarterly-sales-analysis"
4. Title: "Add quarterly sales analysis query"
5. Description:
   ```
   This PR adds a new SQL query for quarterly sales analysis with:
   - Year-over-year comparison
   - Regional breakdown
   - Product category filtering
   
   The query uses common table expressions for better readability and
   includes parameter documentation.
   
   Fixes #42
   ```
6. Add reviewers with SQL expertise
7. Submit the pull request

"Beginning Git and GitHub" (Tsitoara, 2024, p.169) explains that pull requests provide a formal way to ask for permission to apply changes.

#### 6. Code Review Process

Reviewers might comment:
- "Consider adding an index hint for the orders table."
- "Can we format the query to show percentages with % sign?"

Make requested changes:
```bash
# Make changes to the file
git add queries/sales/quarterly_analysis.sql
git commit -m "Add index hint and format percentages per review feedback"
git push origin feature/quarterly-sales-analysis
```

#### 7. Merge the Pull Request

After approval:
1. Click "Merge pull request" on GitHub
2. Confirm the merge
3. GitHub automatically closes the issue (#42)

#### 8. Clean Up

Delete the feature branch:
```bash
git checkout main
git pull origin main
git branch -d feature/quarterly-sales-analysis
```

#### 9. Update the Project Board

The issue automatically moves to "Done" on your project board.

## Advanced Git and GitHub Topics Not Covered

This introduction provides a solid foundation for getting started with Git and GitHub, but there are many advanced features and capabilities not covered here. To continue your learning journey, here are some important topics to explore next.

### Table of Contents for Advanced Topics
- [GitHub Pages](#github-pages)
- [GitHub Actions](#github-actions)
- [GitHub Wikis](#github-wikis)
- [Advanced Git Commands and Features](#advanced-git-commands-and-features)
- [GitHub Project Management](#github-project-management)
- [Git Aliases and Configuration](#git-aliases-and-configuration)
- [Troubleshooting Common Git Problems](#troubleshooting-common-git-problems)

### GitHub Pages
GitHub Pages allows you to host websites directly from your GitHub repositories. This feature is excellent for creating project documentation, personal portfolios, or simple web applications. Learn more in Chapter 17, "More with GitHub" (p.270-274).

### GitHub Actions
GitHub Actions provides powerful automation and CI/CD (Continuous Integration/Continuous Deployment) capabilities. You can automate workflows like testing, building, and deploying your code whenever you push changes. This topic is beyond the scope of the book but is well-documented in GitHub's official documentation.

### GitHub Wikis
For more comprehensive project documentation beyond the README file, GitHub Wikis offer a full-featured documentation system. This feature is covered in Chapter 17, "More with GitHub" (p.267-270).

### Advanced Git Commands and Features
- **Git Stashing**: Save changes temporarily without committing them. See Chapter 16, "Advanced Git" (p.255-260).
- **Git Rebase**: An alternative to merging that creates a cleaner project history. This topic is briefly mentioned in Chapter 14, "More About Conflicts" (p.290-291).
- **Git Hooks**: Custom scripts that run before or after Git events like commit or push. This advanced topic is not covered in the book.
- **Git Bisect**: A binary search tool to find which commit introduced a bug. This topic is not covered in the book.

### GitHub Project Management
More advanced project management features include:
- **Milestones**: Group issues and pull requests for specific project phases or releases. See Chapter 17, "More with GitHub" (p.277-281).
- **GitHub Projects (Advanced)**: Create custom workflows and automation for your project boards. This is briefly covered in Chapter 17, "More with GitHub" (p.277-281).
- **Release Management**: Create tagged releases with bundled binaries and release notes. See Chapter 17, "More with GitHub" (p.274-277).

### Git Aliases and Configuration
Customize your Git experience by creating shortcuts for commonly used commands. Learn more in Chapter 20, "Making Git Yours with Aliases" (p.301-306).

### Troubleshooting Common Git Problems
When you encounter issues with Git, Chapter 18, "Common Git Problems" (p.283-294) provides solutions to many frequent challenges.

As you become more comfortable with the basics, exploring these advanced topics will help you leverage the full power of Git and GitHub for your development workflow. Remember that Git is a deep tool with many capabilities – it's normal and expected to learn new features as you need them rather than trying to master everything at once.