
# Influencer Marketing Platform

An **Influencer Marketing Platform** built with Flask that enables collaboration between sponsors and influencers. The platform allows sponsors to create and manage campaigns, send ad requests to influencers, and track collaboration progress. It also provides admins with comprehensive tools to manage users, campaigns, and ad requests.

## Features

### Admin Features
- **Dashboard Overview**: View statistics like total users, campaigns, flagged users, and ad requests.
- **User Management**: Create, edit, delete, and flag/unflag users.
- **Campaign Management**: Oversee all campaigns, edit, or delete campaigns.
- **Ad Request Management**: Monitor ad requests and manage their status.
- **Analytics**: Access platform-wide analytics.

### Sponsor Features
- **Dashboard**: View and manage campaigns.
- **Campaign Management**: Create, edit, and delete campaigns.
- **Ad Requests**: Create and send ad requests to influencers.
- **Search Influencers**: Filter influencers by username or niche.
- **Collaboration Management**: Track all ad requests and collaborations.
- **Analytics**: Access campaign-related analytics.

### Influencer Features
- **Dashboard**: View received ad requests and their status.
- **Ad Request Management**: Respond to ad requests with payment details and acceptance status.
- **Campaign Search**: Find public campaigns matching their niche.
- **Profile Management**: Update profile details including username, niche, and reach.
- **Analytics**: Access influencer-specific analytics.

### Authentication
- Role-based authentication and session management.
- Secure login and registration with role selection.

---

## Project Structure

```
project/
│
├── static/                # Static files (CSS, JS, images)
├── templates/             # HTML templates
│
├── app.py                 # Main application file
├── influencer_platform.db # SQLite database
│
├── README.md              # Project documentation (this file)
```

---

## Installation

### Prerequisites
- Python 3.7+
- Virtual Environment (recommended)
- SQLite (default database)

### Steps
1. **Clone the Repository**
   ```bash
   git clone https://github.com/your-username/influencer-platform.git
   cd influencer-platform
   ```

2. **Set Up a Virtual Environment**
   ```bash
   python -m venv venv
   source venv/bin/activate # On Windows, use `venv\Scripts\activate`
   ```

3. **Install Dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Set Up the Database**
   ```bash
   flask shell
   >>> from app import db
   >>> db.create_all()
   >>> exit()
   ```

5. **Run the Application**
   ```bash
   flask run
   ```
   The application will be available at `http://127.0.0.1:5000/`.

---

## Usage

### Roles
1. **Admin**
   - Log in with `Admin` role to access the admin dashboard and management tools.

2. **Sponsor**
   - Create an account as a sponsor to manage campaigns and collaborations.

3. **Influencer**
   - Create an account as an influencer to find campaigns and respond to ad requests.

### URLs
- **Homepage**: `/`
- **Admin Dashboard**: `/admin/dashboard`
- **Sponsor Dashboard**: `/sponsor/dashboard`
- **Influencer Dashboard**: `/influencer/dashboard`

---

## Key Models

### `User`
| Field       | Type      | Description                       |
|-------------|-----------|-----------------------------------|
| `id`        | Integer   | Primary key                      |
| `username`  | String    | Unique username                  |
| `password`  | String    | User password                    |
| `role`      | String    | Role: Admin, Sponsor, Influencer |
| `niche`     | String    | Niche for influencers            |
| `reach`     | Integer   | Influencer reach                 |
| `flagged`   | Boolean   | Flagged status                   |

### `Campaign`
| Field         | Type    | Description                        |
|---------------|---------|------------------------------------|
| `id`          | Integer | Primary key                       |
| `name`        | String  | Campaign name                     |
| `description` | Text    | Campaign details                  |
| `start_date`  | Date    | Start date                        |
| `end_date`    | Date    | End date                          |
| `budget`      | Float   | Campaign budget                   |
| `visibility`  | Boolean | Public or private visibility      |
| `sponsor_id`  | Integer | Foreign key to the sponsor user   |
| `niche`       | String  | Niche category                    |

### `AdRequest`
| Field           | Type    | Description                        |
|-----------------|---------|------------------------------------|
| `id`            | Integer | Primary key                       |
| `campaign_id`   | Integer | Foreign key to the campaign       |
| `influencer_id` | Integer | Foreign key to the influencer     |
| `messages`      | Text    | Communication details             |
| `requirements`  | Text    | Ad requirements                   |
| `payment_amount`| Float   | Agreed payment amount             |
| `status`        | String  | Status: Pending, Accepted, Rejected |

---

## Screenshots

### Admin Dashboard



### Sponsor Dashboard
![image](https://github.com/user-attachments/assets/a45fe53c-7fbc-42db-9a21-3a61cd729b31)


### Influencer Dashboard
*Coming Soon*

---

## Contributing
Contributions are welcome! Please follow these steps:
1. Fork the repository.
2. Create a feature branch.
3. Commit your changes.
4. Create a pull request.

---

## License
This project is licensed under the MIT License. See the LICENSE file for details.

---

## Contact
For any inquiries or feedback, please reach out to:
- **Email**: your-email@example.com
- **GitHub**: [your-username](https://github.com/your-username)

