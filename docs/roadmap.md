# Sales Insight Copilot - Learning Roadmap

## 1. Project Overview

Sales Insight Copilot is a learning project designed to build an end-to-end sales analytics application while developing practical skills in software engineering, data engineering, backend development, machine learning, and applied AI.

The project is not only about building a functional application. It is also a structured learning journey that helps the developer understand the technologies, engineering principles, and workflows used in real-world software development.

## 2. Learning Objectives

By completing this roadmap, the developer should be able to:

- Analyze business requirements and translate them into technical requirements.
- Use Git and GitHub for version control and collaboration.
- Work with structured datasets using Python and Pandas.
- Understand relational databases and write SQL queries.
- Perform data cleaning, exploratory data analysis, and business KPI analysis.
- Build backend services and REST APIs.
- Apply software engineering practices such as testing, logging, error handling, and configuration management.
- Understand basic machine learning workflows using Scikit-learn.
- Develop AI-powered features using LLM APIs, embeddings, and RAG.
- Understand essential production tools such as Docker, CI/CD, and deployment.
- Integrate these components into a functional Sales Insight Copilot application.

## 3. Learning Approach

- Study approximately 3 sessions per week.
- Each session is approximately 30 minutes.
- Understand concepts and logic before implementing them.
- Use official documentation and free learning resources whenever possible.
- Use AI coding agents as assistants, not as substitutes for understanding.
- Review, test, and understand generated code.
- Complete the objectives and acceptance criteria of each phase before moving forward.

## 4. Roadmap Overview

| Phase | Main Focus | Duration | Status |
|---|---|---:|---|
| 1 | Project Discovery and Version Control | Weeks 1–2 | Completed |
| 2 | Dataset Engineering | Weeks 3–4 | In Progress |
| 3 | SQL and Data Analytics | Weeks 5–8 | Not Started |
| 4 | Backend Development | Weeks 9–12 | Not Started |
| 5 | Production Engineering | Weeks 13–16 | Not Started |
| 6 | Machine Learning and Applied AI | Weeks 17–22 | Not Started |
| 7 | Integration and Deployment | Weeks 23–24 | Not Started |

## 5. Detailed Roadmap

### Phase 1 - Project Discovery and Version Control

#### Week 1: Requirements Analysis

Objectives:
- Understand the business problem.
- Identify target users and their needs.
- Define project scope and objectives.
- Identify business KPIs.
- Write user stories and acceptance criteria.

Expected Deliverables:
- requirements.md
- user_stories.md
- acceptance_criteria.md
- kpi_definitions.md

Status: Completed.

#### Week 2: Git and GitHub

Objectives:
- Understand Git fundamentals.
- Learn repository initialization and version control.
- Understand commits, branches, and remote repositories.
- Connect the local project to GitHub.
- Understand basic collaboration workflows.

Expected Deliverables:
- Git repository.
- GitHub remote repository.
- .gitignore
- Initial project history.

Status: Completed.

### Phase 2 - Dataset Engineering

#### Week 3: Data Modeling and Dataset Generation

Objectives:
- Understand CSV and Pandas DataFrames.
- Understand data types and structured data.
- Design relational data structures.
- Understand Primary Keys and Foreign Keys.
- Generate synthetic sales datasets using Python and Pandas.

Expected Deliverables:
- data_dictionary.md
- customers.csv
- products.csv
- orders.csv
- order_items.csv
- generate_data.py
- inspect_data.py

Completion Criteria:
- All datasets follow the defined data model.
- Primary Keys are valid and unique.
- Foreign Key relationships are valid.
- Missing values and duplicate records can be detected.

Status: Not Started.

#### Week 4: Data Cleaning and Exploratory Data Analysis

Objectives:
- Understand common data quality problems.
- Handle missing values and duplicate records.
- Validate data types and inconsistent values.
- Perform Exploratory Data Analysis (EDA).
- Identify initial patterns and trends in sales data.

Expected Deliverables:
- clean_data.py
- cleaned datasets.
- data_quality_report.md
- exploratory_data_analysis.ipynb or equivalent analysis scripts.
- Initial sales analysis report.

Completion Criteria:
- Cleaning rules are documented.
- Data quality issues are handled according to defined rules.
- Basic sales patterns and trends can be explained.

Status: Not Started.

### Phase 3 - SQL and Data Analytics

#### Week 5: SQL Fundamentals

Objectives:
- Understand relational databases.
- Learn SELECT, WHERE, ORDER BY, and LIMIT.
- Learn aggregate functions.
- Understand GROUP BY and HAVING.

Expected Deliverables:
- sql_basics.sql
- Basic sales queries.

#### Week 6: Relational Queries

Objectives:
- Understand INNER JOIN and LEFT JOIN.
- Understand relationships between tables.
- Learn subqueries and Common Table Expressions (CTEs).
- Practice querying multiple related sales tables.

Expected Deliverables:
- sql_joins.sql
- sql_analysis_queries.sql

#### Week 7: Business Metrics and KPI Analysis

Objectives:
- Calculate total revenue and order count.
- Analyze Average Order Value (AOV).
- Analyze customer purchasing behavior.
- Analyze product and category performance.
- Translate business questions into SQL queries.

Expected Deliverables:
- sales_kpi_queries.sql
- kpi_analysis.md

#### Week 8: Data Visualization and Reporting

Objectives:
- Understand basic data visualization principles.
- Select appropriate charts for business metrics.
- Visualize revenue, orders, and product performance.
- Communicate analytical findings clearly.

Expected Deliverables:
- sales_visualization.ipynb or equivalent.
- Initial sales dashboard or report.

### Phase 4 - Backend Development

#### Week 9: Python Project Structure and Environment Management

Objectives:
- Organize Python applications into modules.
- Understand virtual environments.
- Manage dependencies.
- Understand configuration files.
- Apply basic exception handling.

Expected Deliverables:
- Organized backend project structure.
- requirements.txt or equivalent dependency configuration.
- Basic configuration module.

#### Week 10: REST API and FastAPI Fundamentals

Objectives:
- Understand HTTP and REST API concepts.
- Learn HTTP methods and status codes.
- Build API endpoints using FastAPI.
- Understand request and response structures.
- Explore automatically generated API documentation.

Expected Deliverables:
- Initial FastAPI application.
- Basic sales API endpoints.

#### Week 11: Database Integration

Objectives:
- Connect the backend to a relational database.
- Understand database models and schemas.
- Perform database queries from the backend.
- Understand data validation using Pydantic.
- Implement basic data access operations.

Expected Deliverables:
- Database integration.
- Database models.
- Sales data retrieval endpoints.

#### Week 12: Backend CRUD and API Testing

Objectives:
- Implement basic CRUD operations.
- Understand API validation and error handling.
- Learn automated API testing.
- Test endpoints using appropriate testing tools.

Expected Deliverables:
- Functional API endpoints.
- API tests.
- Basic API documentation.

### Phase 5 - Production Engineering

#### Week 13: Software Testing

Objectives:
- Understand unit testing and integration testing.
- Learn Pytest fundamentals.
- Write tests for business logic and data operations.
- Understand test coverage and test-driven feedback.

Expected Deliverables:
- Test suite.
- Documented test cases.

#### Week 14: Logging and Error Handling

Objectives:
- Understand application logging.
- Distinguish different log levels.
- Handle application errors consistently.
- Understand debugging and troubleshooting workflows.

Expected Deliverables:
- Logging configuration.
- Consistent error handling.

#### Week 15: Configuration and Security Fundamentals

Objectives:
- Manage environment variables.
- Understand .env files and secret management.
- Avoid exposing sensitive information.
- Understand basic API security and input validation.

Expected Deliverables:
- Environment-based configuration.
- Updated .gitignore.
- Basic security checklist.

#### Week 16: Docker and CI/CD Fundamentals

Objectives:
- Understand containers and Docker.
- Create a Dockerfile.
- Understand Docker Compose.
- Understand Continuous Integration and Continuous Deployment.
- Explore automated testing workflows.

Expected Deliverables:
- Dockerfile.
- Docker Compose configuration where appropriate.
- Basic CI workflow.

### Phase 6 - Machine Learning and Applied AI

#### Week 17: Machine Learning Fundamentals

Objectives:
- Understand supervised and unsupervised learning.
- Understand features, labels, and datasets.
- Learn training and testing data separation.
- Understand basic regression and classification workflows.

Expected Deliverables:
- Machine learning learning notes.
- Initial Scikit-learn experiment.

#### Week 18: Model Training and Evaluation

Objectives:
- Train a basic machine learning model.
- Understand model evaluation metrics.
- Learn basic feature preprocessing.
- Understand overfitting and generalization.

Expected Deliverables:
- Initial ML model.
- Model evaluation report.

#### Week 19: LLM Fundamentals and API Integration

Objectives:
- Understand Large Language Models.
- Understand tokens, context windows, and model limitations.
- Learn to call LLM APIs.
- Understand prompt engineering fundamentals.

Expected Deliverables:
- Initial LLM API integration.
- Prompt experiments.

#### Week 20: Structured Outputs and AI Tool Usage

Objectives:
- Understand structured outputs.
- Learn how to request reliable JSON responses.
- Understand function calling and tool usage.
- Integrate AI outputs with backend application logic.

Expected Deliverables:
- Structured LLM responses.
- Initial AI-assisted sales analysis feature.

#### Week 21: Embeddings and Vector Search

Objectives:
- Understand text embeddings.
- Understand semantic similarity.
- Explore vector databases and vector search.
- Understand when vector search is appropriate.

Expected Deliverables:
- Embedding experiment.
- Basic semantic search implementation.

#### Week 22: Retrieval-Augmented Generation (RAG)

Objectives:
- Understand the RAG architecture.
- Learn document preparation and chunking.
- Build a basic retrieval pipeline.
- Combine retrieved information with LLM responses.
- Understand grounding and hallucination risks.

Expected Deliverables:
- Basic RAG pipeline.
- RAG experiment report.

### Phase 7 - Integration and Deployment

#### Week 23: Sales Insight Copilot Integration

Objectives:
- Integrate data analytics, backend, and AI components.
- Connect AI features with sales data.
- Implement the main user workflows.
- Evaluate output quality and reliability.
- Test the complete application.

Expected Deliverables:
- Integrated Sales Insight Copilot application.
- End-to-end tests.
- Application usage documentation.

#### Week 24: Deployment and Final Review

Objectives:
- Deploy the application to an appropriate environment.
- Verify application functionality after deployment.
- Review security, configuration, and reliability.
- Complete project documentation.
- Prepare a project demonstration for CV and portfolio.

Expected Deliverables:
- Deployed application.
- Final README.md.
- Architecture documentation.
- Project demonstration.
- Final review report.

## 6. Progress Tracking

A phase should only be marked as Completed when:
- Its learning objectives have been covered.
- Expected deliverables have been reviewed.
- Completion criteria have been satisfied.
- The developer can explain the key concepts and implementation decisions.

The roadmap should be updated as the project evolves. Changes to the order or scope of future phases should be discussed before implementation.