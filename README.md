
![osTicket logo](https://i.imgur.com/Clzj7Xs.png)

# osTicket - Prerequisites and Installation

This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.

---

## Environments and Technologies Used

- Microsoft Azure (Virtual Machines)
- Remote Desktop
- Internet Information Services (IIS)

---

## Operating Systems Used

- Windows 10 (21H2)

---

## Prerequisites

- Create an Azure Virtual Machine running Windows 10 with 4 vCPUs

![Azure VM setup](https://github.com/user-attachments/assets/4e04513f-a178-42ef-9e4e-874a6bbdcfbd)

---

## Installation Steps

1. Within the VM (osticket-vm), download the `osTicket-Installation-Files.zip` and unzip it onto your desktop. The folder should be called **osTicket-Installation-Files**. We will use the files in this folder to install osTicket and its dependencies.

   ![Unzipped folder](https://github.com/user-attachments/assets/214d44e7-4504-41f7-b196-e199cc18ffb6)

2. Install / Enable IIS in Windows **WITH CGI**  
   Navigate: World Wide Web Services -> Application Development Features -> **[X] CGI**

   ![IIS CGI feature](https://github.com/user-attachments/assets/97255c0f-f641-4ecd-8aac-7e3887dfeb28)

3. From the **osTicket-Installation-Files** folder:  
   - Install **PHP Manager for IIS** (`PHPManagerForIIS_V1.5.0.msi`)

   ![PHP Manager](https://github.com/user-attachments/assets/cfd7b4bf-6bca-447d-ba97-d0034cebeb5a)

4. From the **osTicket-Installation-Files** folder:  
   - Install **Rewrite Module** (`rewrite_amd64_en-US.msi`)

   ![Rewrite Module](https://github.com/user-attachments/assets/991e434d-f194-41c4-b197-80a1f5157c0c)

5. Create the directory `C:\PHP`

   ![Create PHP folder](https://github.com/user-attachments/assets/995b0836-1e16-4653-80c8-24c801ff77db)

6. From the **osTicket-Installation-Files** folder:  
   - Unzip PHP 7.3.8 (`php-7.3.8-nts-Win32-VC15-x86.zip`) into the `C:\PHP` folder

   ![PHP unzip](https://github.com/user-attachments/assets/2aefde21-0aad-4b84-93e8-bd489882c675)

7. From the **osTicket-Installation-Files** folder:  
   - Install **VC_redist.x86.exe**

   ![VC redist install](https://github.com/user-attachments/assets/5cb63d1e-548a-4eae-a0b5-fd22fb04415a)

8. From the **osTicket-Installation-Files** folder:  
   - Install **MySQL 5.5.62** (`mysql-5.5.62-win32.msi`)  
   Typical Setup -> Launch Configuration Wizard -> Standard Configuration

   ![MySQL setup](https://github.com/user-attachments/assets/fadcf814-f751-4f32-9a00-bc6f7c733086)

9. Open IIS **as Administrator**, register PHP from within IIS:  
   - Go to PHP Manager -> Register new PHP version at `C:\PHP\php-cgi.exe`  
   - Reload IIS (Stop and Start server)

   ![Register PHP in IIS](https://github.com/user-attachments/assets/f450d093-54d5-4b9a-9396-cbf51c92a3b4)

10. Install osTicket v1.15.8  
    - From **osTicket-Installation-Files** folder, unzip `osTicket-v1.15.8.zip`  
    - Copy the **upload** folder into `C:\inetpub\wwwroot`  
    - Rename **upload** folder to **osTicket**  
    - Reload IIS (Stop and Start server)

    ![osTicket folder](https://github.com/user-attachments/assets/36758585-0be4-4413-a801-852d04ec9ce6)

11. In IIS:  
    - Go to **Sites** -> **Default Web Site** -> **osTicket**  
    - Click **Browse *:80** on the right pane

    ![Browse site](https://github.com/user-attachments/assets/34cce359-2a23-4cde-a3d8-523c1628656d)

12. Enable PHP extensions missing in the default installation:  
    - In IIS, double-click **PHP Manager**  
    - Click **Enable or disable an extension**  
    - Enable: `php_imap.dll`, `php_intl.dll`, `php_opcache.dll`  
    - Refresh the osTicket site in your browser

    ![Enable PHP extensions](https://github.com/user-attachments/assets/77436053-e02c-44c6-a6e3-ccbbe53af432)

13. Rename `ost-sampleconfig.php` to `ost-config.php`  
    Location: `C:\inetpub\wwwroot\osTicket\include\`

    ![Rename config](https://github.com/user-attachments/assets/a27de6f3-aa3e-4f87-a311-7ac70be74e50)

14. Set permissions on `ost-config.php`:  
    - Disable inheritance -> Remove all existing permissions  
    - Add **Everyone** group with **Full Control**

    ![Set permissions](https://github.com/user-attachments/assets/1b039ec3-294b-4cfa-bf0b-15064890fc50)

15. Continue setting up osTicket in the browser:  
    - Click **Continue**  
    - Set the helpdesk name (e.g., **Helpdesk**)  
    - Set default email (receives customer emails)

    ![Setup osTicket](https://github.com/user-attachments/assets/002c2bfa-3ccd-455b-a1c9-6a4e65dcc12a)

16. From the **osTicket-Installation-Files** folder, install **HeidiSQL**  
    - Open HeidiSQL  
    - Create a new session with username: `root` and password: `root`  
    - Connect and create a new database called **osTicket**

    ![HeidiSQL create db](https://github.com/user-attachments/assets/244b9ccc-4a97-41e3-b3b2-63ee3480bd36)

17. Continue setting up osTicket in the browser:  
    - Database: **osTicket**  
    - MySQL Username: `root`  
    - MySQL Password: `root`  
    - Click **Install Now!**

    ![Final install](https://github.com/user-attachments/assets/ae559643-8539-45d6-a0c5-4ef18957ee21)

---

Congratulations! You have successfully installed and configured osTicket on your Azure VM using IIS and MySQL.

---

