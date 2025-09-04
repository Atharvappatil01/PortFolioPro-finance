# 📈 PortFolioPro

**PortFolioPro** is a full-stack web application that enables users to manage their financial portfolios across **stocks, real estate, cryptocurrency, and bank accounts**.  
Built with **object-oriented design principles** and **PostgreSQL** for data persistence, the system emphasizes scalability, maintainability, and extensibility.

---

## 🔎 Overview
The platform provides:
- Secure authentication and user portfolio management  
- Support for multiple account types (stocks, crypto, banks, real estate)  
- Consistent data handling using design patterns (Factory, Strategy, Singleton)  
- Rich portfolio visualizations to make financial insights accessible  

---

## 🏗️ Project Structure
```
project_root/
│
├── app/
│   ├── __init__.py           # Flask application initialization
│   ├── routes/               # API endpoints
│   ├── database/             # Database management
│   ├── models/               # Model logic (users, accounts, assets, etc.)
│   ├── factories/            # Factory implementations (factory pattern)
│   ├── visualizations/       # Visualization strategies (strategy pattern)
│   ├── static/               # CSS/JS files
│   └── templates/            # HTML templates
│
├── config.py                 # Application configuration
└── run.py                    # Application entry point
```

---

## 🧩 OOP Design
### Class Hierarchy
- **User**: Manages authentication and portfolio interactions.  
- **Portfolio**: Holds and manages multiple account types.  
- **Account classes**:
  - `Account` (abstract base)
  - `StockAccount` – Stock investments  
  - `CryptoAccount` – Cryptocurrency holdings  
  - `BankAccount` – Traditional banking  
- **Asset classes**:
  - `Asset` (abstract base)  
  - `Stock` – Represents stock holdings  
  - `Crypto` – Represents crypto holdings  
  - `Cash` – Represents liquid holdings  

A `User` object owns one `Portfolio`. The portfolio aggregates `Accounts`, and each account manages multiple `Assets`.  

**User Flow:**  
`Home Page → View Portfolio → Add Account → Add Asset → Visualize`

---

## 🎨 Design Patterns
- **Factory Method** → Simplified creation of assets and accounts  
- **Strategy Pattern** → Plug-and-play visualization options  
- **Singleton** → Database manager ensures consistent DB connection  

---

## 🗄️ Database Schema
The system uses **PostgreSQL**, with a relational schema:

- **Users** → Stores authentication and profile data  
- **Portfolios** → Links to users  
- **Accounts** → Holds account-specific data  
- **Assets** → Stores assets (stock, crypto, cash, etc.) linked to accounts  

---

## ✅ Current Features
- 🔐 User Authentication  
- 📊 Account & Asset Management  
- 🗄️ Database Integration with PostgreSQL  
- 📈 Multiple Visualization Options (charts, pie, bar)  

---

## ⚙️ Installation and Setup

### 1. Clone Repository
```bash
git clone https://github.com/<your-username>/portfolio-pro.git
cd portfolio-pro
```

### 2. Install Requirements
```bash
pip install -r requirements.txt
```

### 3. Database Setup
- Create a PostgreSQL DB called **`portfolio_management`**  
- Use `pgAdmin` or CLI to execute the schema script:  
  ```sql
  -- In pgAdmin Query Tool:
  \i app/database/db_setup.sql
  ```
- Update `config.py` → set `DB_PASSWORD`  

### 4. Run the Application
```bash
python run.py
```

### 5. Reset DB (if needed)
Run `app/database/clear_db.sql` inside pgAdmin or psql.

---

## 🚀 Example Usage
**Step 1:** Login or Register  
![Login UML](./uml_diagram.png)

**Step 2:** Add Account(s) to Portfolio  
![Add Account](./stocks_updated.png)

**Step 3:** Add Assets and Visualize Portfolio  
![Visualization](./pie_chart_updated.png)

---

## 🌟 Benefits
- **Maintainability** → Clean separation of concerns, extensible architecture  
- **User Experience** → Intuitive flow, multiple visualizations, easy navigation  
- **Data Integrity** → Singleton DB manager ensures consistency, cascading deletes maintain referential integrity  

---

## 🔮 Future Features
- Stock & Crypto API Integration  
- Extended Visualizations (heatmaps, timelines)  
- Additional Asset Types (ETFs, bonds, real estate)  

---

## 🏁 Conclusion
**PortFolioPro** blends **robust software design** with **practical usability**.  
Its clean architecture and design patterns make it highly maintainable and extensible, while the intuitive interface ensures value for users managing diverse financial assets.

---

## 📊 UML Diagram
Here’s a UML diagram of the system design:

![UML Diagram](./uml_diagram.png)

---

### License
MIT License — free to use and extend with attribution.
