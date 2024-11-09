# 📊 Pixela Habit Tracker Integration

A Python script to track daily activities (like cycling) using the **Pixela** API. This project automates the process of adding, updating, and deleting records on a graph in Pixela.

---

## 📜 Overview

This script connects to [Pixela](https://pixe.la/) to create a habit-tracking graph and log data for a specified activity, such as kilometers cycled. Users can add, update, or delete daily activity records using Pixela's API.

---

## 📦 Features

- **Create User**: Automatically register a new user on Pixela.
- **Create Graph**: Set up a new graph to visualize progress over time.
- **Add Daily Record**: Log daily activity data to the graph.
- **Update Record**: Modify an existing daily entry.
- **Delete Record**: Remove a specific daily entry.

---

## 🛠️ Setup and Installation

1. **Clone this repository**:
   ```bash
   git clone https://github.com/username/pixela-habit-tracker.git
    ```
2. Install Dependencies: Ensure requests is installed:
```bash
pip install requests
```
3. Configure Environment Variables: Add your Pixela credentials directly in the script or manage them securely using environment variables.
4. Define Constants: Replace placeholders in the script with your own values:
```python
USERNAME = "YOUR_USERNAME"
TOKEN = "YOUR_TOKEN"
GRAPH_ID = "YOUR_GRAPH_ID"
```
---
## 📄 How It Works
### Step 1: Create User (One-Time Setup)
To create a new Pixela user, uncomment and execute the POST request to the pixela_endpoint:
```python
response = requests.post(url=pixela_endpoint, json=user_params)
```
### Step 2: Create Graph (One-Time Setup)
Uncomment and execute the following section to create a graph for tracking your habit:
```python
response = requests.post(url=graph_endpoint, json=graph_config, headers=headers)
```
### Step 3: Add Daily Record
Prompts the user to enter daily data (e.g., kilometers cycled) and logs it to the graph:
```python
pixel_data = {
    "date": today.strftime("%Y%m%d"),
    "quantity": input("How many kilometers did you cycle today? "),
}
response = requests.post(url=pixel_creation_endpoint, json=pixel_data, headers=headers)
```
### Step 4: Update Record
To update an existing record, modify new_pixel_data and send a PUT request:
```python
new_pixel_data = {"quantity": "4.5"}
response = requests.put(url=update_endpoint, json=new_pixel_data, headers=headers)
```
### Step 5: Delete Record
To delete a specific record, execute a DELETE request:
```python
response = requests.delete(url=delete_endpoint, headers=headers)
```
---
## 📌 Notes
- Token: Pixela uses a token for authentication. Use a secure, unique token.
- Date Format: Ensure the date is in YYYYMMDD format.
- Color Options: Pixela supports a variety of colors for graph customization, such as shibafu, momiji, sora, ichou, and ajisai.
---
## 🔗 Additional Resources
- Pixela API Documentation
---
## 📧 Contact
For any questions or issues, feel free to reach out!
