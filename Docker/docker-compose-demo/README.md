# 🚀 Docker Compose Demo – WordPress + MySQL

This project demonstrates how to set up a **WordPress site** with a **MySQL database** using Docker Compose.  

## 📂 Project Structure
```
docker-compose-demo/
│── docker-compose.yml
```

## 🛠 Steps Performed

1. **Created Project Folder**
   ```bash
   D:
   mkdir docker-compose-demo
   cd docker-compose-demo
   ```

2. **Added `docker-compose.yml` File**  
   Example file:
   ```yaml
   version: '3.8'

   services:
     wordpress:
       image: wordpress:latest
       ports:
         - "8081:80"
       environment:
         WORDPRESS_DB_HOST: db:3306
         WORDPRESS_DB_USER: wp_user
         WORDPRESS_DB_PASSWORD: wp_pass
         WORDPRESS_DB_NAME: wp_database
       depends_on:
         - db

     db:
       image: mysql:5.7
       environment:
         MYSQL_ROOT_PASSWORD: root_password
         MYSQL_DATABASE: wp_database
         MYSQL_USER: wp_user
         MYSQL_PASSWORD: wp_pass
       volumes:
         - db_data:/var/lib/mysql

   volumes:
     db_data:
   ```

3. **Start Services**
   ```bash
   docker-compose up -d
   ```

4. **Verify Running Containers**
   ```bash
   docker ps
   ```
   ✅ Containers for `wordpress` and `mysql` are running.

5. **Open WordPress in Browser**  
   Go to:  
   ```
   http://localhost:8081
   ```
   _(![alt text](<Screenshot (72)-1.png>))_

6. **Fill WordPress Setup Info**  
   - Site Title  
   - Username & Password  
   - Email  

   _(![alt text](<Screenshot (73)-1.png>))_

7. **Login to WordPress**  
   - Access the WordPress admin panel.  
   - Website page opened successfully.  

   _(![alt text](<Screenshot (74)-1.png>))_

8. **Stop and Remove Containers with Volumes**
   ```bash
   docker-compose down -v
   ```

9. **Verify Containers Stopped**
   ```bash
   docker ps
   ```
   ✅ No containers running.

---

## 📸 Screenshots  
- [ ] WordPress installation screen  
- [ ] WordPress login/dashboard  
- [ ] Running containers (`docker ps`)  

---

## ✅ Summary
- Launched **WordPress + MySQL** using Docker Compose  
- Accessed the site at `localhost:8081`  
- Successfully logged in and viewed WordPress  
- Removed containers and volumes after use  

---

👉 This repo serves as a simple **Docker Compose learning project** to set up a working WordPress site locally.  
