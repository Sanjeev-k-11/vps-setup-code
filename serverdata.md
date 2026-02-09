# 🍃 Repido Database Management Guide

This guide provides a structured overview of common **MongoDB** commands used for managing the `repido` project database on a VPS environment.

---

## 🚀 1. Getting Started
Connect to the database and navigate through collections.

| Task | Command |
| :--- | :--- |
| **Enter Mongo Shell** | `mongosh` |
| **List Databases** | `show dbs` |
| **Select Project DB** | `use repido` |
| **List Collections** | `show collections` |

---

## 🔍 2. Reading Data
View records from the main collections. `.pretty()` is used for readable formatting.

### 👤 User Records
```javascript
db.users.find().pretty()
```

##🏎️ Driver Records

```javascript
db.drivers.find().pretty()
```

## 🛣️ Ride Records

```javascript
db.rides.find().pretty()
```

## 💳 Transaction Records

```javascript
db.transactions.find().pretty()
```
## 🎯 3. Targeted Queries
Find specific data or get statistics.
##Search Ride by ID:


```javascript
db.rides.find({ _id: ObjectId("PASTE_ID_HERE") })
```
## Total Count of Rides:

```javascript
db.rides.countDocuments()
```


 ## ⚠️ 4. Data Maintenance (Danger Zone)
Commands for deleting records. **Use with caution!**

| Level | Action | Command |
| :--- | :--- | :--- |
| 🟢 **Safe** | Delete One Ride | `db.rides.deleteOne({ _id: ObjectId("ID") })` |
| 🔴 **Danger** | **Delete ALL Rides** | `db.rides.deleteMany({})` |

---

## 💡 5. Pro-Tips for VPS
Efficiency commands for handling large datasets smoothly:

*   **View Latest 5 Rides:**
    ```javascript
    db.rides.find().sort({ $natural: -1 }).limit(5).pretty()
    ```
*   **Clear Shell Screen:**
    Type `cls` or press `Ctrl + L`.
*   **Check MongoDB Status:**
    *(Run this outside the mongo shell)*
    ```bash
    sudo systemctl status mongod
    ```

---

## 📤 6. Exit Session
To safely exit the Mongo shell and return to your VPS terminal:

```bash
exit
```

### Is code mein kya khaas hai?
1.  **Tables:** Delete commands ko table mein rakha hai taaki "Safe" aur "Danger" alag se dikhe.
2.  **Syntax Highlighting:** JavaScript aur Bash ke liye alag se code blocks use kiye hain.
3.  **Visual Aids:** Emojis (🟢, 🔴, 💡, 📤) ka use kiya hai taaki reading boring na ho.
4.  **Quote Block:** Footer ko ek stylish quote block mein dala hai.

Aap ise kisi bhi Markdown editor ya GitHub/GitLab par check karenge toh yeh bahut hi clean dikhega!
