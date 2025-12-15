# 🧑‍💻 How to Create a New User in Active Directory

This guide outlines the steps to create a new user account within Active Directory Users and Computers (ADUC) on a Windows Server.

---

## Step 1: Launch Active Directory Users and Computers (ADUC)

1.  Open **Server Manager**.
2.  In the top right corner, click on **Tools**.
3.  Select **Active Directory Users and Computers** from the dropdown menu.


<img width="1612" height="919" alt="Server- Users and Computers" src="https://github.com/user-attachments/assets/b46571ba-5010-4b4c-a1c8-27d5b8b89e3b" />

## Step 2: Initiate New User Creation

1.  In the **Active Directory Users and Computers** window, navigate the console tree on the left.
2.  **Right-click** the Organizational Unit (OU) or container where you want to place the new user (e.g., your domain name or the default **Users** container).
3.  From the context menu, select **New**, and then click **User**.


<img width="1916" height="1075" alt="Windows Server 2022 - User Creation" src="https://github.com/user-attachments/assets/083103fd-80b7-43eb-9ee6-f39d69f3d66b" />

4.  The **New Object - User** wizard will appear. Fill in the required details:
    * **First name** and **Last name**.
    * **Full name** (this is automatically generated but can be changed).
    * **User logon name** (This is the username the user will use to log in).

## Step 3: Set Password and Account Options

1.  Click **Next**. You will be prompted to set the new user's password.
2.  Enter a password that adheres to your organization's **password policy** in both the **Password** and **Confirm password** fields.


<img width="1607" height="901" alt="Server - User Creation" src="https://github.com/user-attachments/assets/808bab48-1dec-42a1-8877-b1587ec6e52c" />

3.  Select the appropriate **Password Options**:
    * **User must change password at next logon** (Recommended for new accounts).
    * **User cannot change password**.
    * **Password never expires**.
    * **Account is disabled** (Useful if the account shouldn't be active immediately).
4.  Click **Next**, then click **Finish** to create the user account.

---

## Step 4: User Login and Domain Joining Prerequisite

Once the user is created in Active Directory, they can log in to a domain-joined machine.

* **Prerequisite:** Before the user attempts to log in to their computer, ensure the computer has been properly **joined to the domain**. Please refer to the **Domain Join Steps** guide within this repository for instructions.
