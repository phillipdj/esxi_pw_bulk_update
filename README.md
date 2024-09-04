ESXi Password Bulk Update Script
This repository contains a Python script designed to automate the process of changing passwords on ESXi hosts via SSH. The script connects to each ESXi host using SSH and updates the password for the specified user.

Features
Automated Password Change: The script automates the process of connecting to each ESXi host and changing the password.
Excel Integration: IP addresses of the ESXi hosts are read from an Excel file, allowing easy management of the list of devices.
Error Handling: The script includes basic error handling for issues such as authentication failures and SSH connection problems.
Prerequisites
Before running the script, ensure you have the following installed:

Python 3.x
Required Python packages: paramiko, pandas, openpyxl (for reading Excel files)
You can install the necessary packages using pip:

sh
Copy code
pip install paramiko pandas openpyxl
Usage
Prepare the Excel File: Create an Excel file (esxi_pw_bulk_update_ip_addresses.xlsx) with the following structure:

Sheet Name: IP Addresses (or change the sheet_name variable in the script)
Column Name: IP (or change the column_name variable in the script)
The column should contain the IP addresses of the ESXi hosts you want to update.

Update the Script:

New Password: Replace "New password here" with the new password you want to set.
Current Password: Replace "Current password here" with the current password for the ESXi hosts.
Username: Replace "root" with the username you want to use (if different from root).
Port: If your ESXi hosts use a different SSH port, update the port variable accordingly.
Run the Script:

sh
Copy code
python esxi_password_update.py
The script will read the list of IP addresses from the Excel file, connect to each ESXi host, and attempt to change the password.

Error Handling
The script will print error messages for any host where the password change fails, including issues such as authentication failures or SSH connection errors.

Customization
Commands: You can modify the change_esxi_password function to execute different commands if needed.
Device Type: If you're working with a different type of device, you may need to adjust the connection method or command syntax accordingly.
Contribution
Contributions are welcome! Feel free to fork this repository, submit pull requests, or open issues for any bugs or feature requests.

License
This project is licensed under the MIT License. See the LICENSE file for details.
