<img align="right" src="https://visitor-badge.laobi.icu/badge?page_id=noetovar5.learnlinuxlesson3"/>
# learnlinuxlesson3

youtube tutorial learn linux lesson 3


This is a follow along guide for youtube video learn linux lesson2
Below is a step-by-step guide to set up a new Ubuntu server for two clients named Bob and Sophia, fulfilling their user-specific requirements.

### Initial Server Setup
1. **Connect to the Server:** Access the server through SSH using the terminal or an SSH client.
   ```
   ssh username@server_ip_address
   ```

2. **Update Packages:** Ensure the server is up to date by running:
   ```
   sudo apt update && sudo apt upgrade
   ```

### User Creation and Privilege Management
3. **Create Users:**
   ```
   sudo adduser bob
   sudo adduser sophia
   ```

4. **Grant Elevated Privileges to Bob:**
   Add Bob to the sudo group to provide sudo privileges.
   ```
   sudo usermod -aG sudo bob
   ```

5. **Password Change on First Login:**
   Notify Bob and Sophia of their login credentials and instruct them to change their passwords upon their initial login.
   ```
   passwd bob
   passwd sophia
   ```

### Directory and File Creation for Each User
6. **Login as Bob and Sophia:**
   Bob and Sophia should log in using their credentials via SSH.

7. **Create Directories and Files:**
   - **Bob (Accounting):**
     ```
     mkdir accounting_directory
     cd accounting_directory
     touch to_do_list.txt
     ```

   - **Sophia (Production):**
     ```
     mkdir production_directory
     cd production_directory
     touch to_do_list.txt
     ```

8. **Rename Files:**
   Within their respective directories, have Bob and Sophia rename the created files:
   ```
   mv to_do_list.txt bob_to_do_list.txt  # For Bob
   mv to_do_list.txt sophia_to_do_list.txt  # For Sophia
   ```

9. **Permissions Adjustments:**
   To ensure proper access control:
   - **Bob's Directory:** Bob should have full access to his directory, others should have no access.
     ```
     chmod 700 accounting_directory
     ```
   - **Sophia's Directory:** Sophia can have read and execute permissions but not write or delete.
     ```
     chmod 755 production_directory
     ```

10. **Exit SSH Sessions:**
    After completing the tasks, exit the SSH sessions:
    ```
    exit
    ```

### Conclusion
This guide provides a structured approach to set up a new Ubuntu server for two clients, configuring user privileges and directing them to create directories, files, and manage their respective access rights. 
Adjustments to directory and file permissions can be made based on specific requirements.

Remember, ensure that the server's firewall is configured properly and only essential ports are open. Regularly update and maintain the server to ensure security and optimal performance.
