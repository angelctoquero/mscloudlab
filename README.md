# Table of Contents
  - [Microsoft 365](#microsoft-365)
  - [Add User](#add-user)
  - [Reset Password](#reset-password)
  - [Entra ID](#entra-id)
  - [Joining Windows 10 to Entra](#joining-windows-10-to-entra-id)
  - [Intune](#intune)
  - [Install App](#install-app)



# Intro
A work in progress to get myself familiar with Microsoft's Entra ID, 365 and Intune.

# Handy Notes
- I signed up for Microsoft 365 Business Premium because it comes with Intune and a 30 day free trial
- I signed up for MS 365 first and Entra ID second
- MS 365 gave me the option of creating my own Outlook email account AND a unique sign-on name with a domain that looked like myname@something.onmicrosoft.com
- When I signed up for Entra ID I should have used the sign-on name I created at MS 365, myname@something.onmicrosoft.com
- Instead I used my new Outlook email which led to Entra ID creating a tenant with a different domain from what my MS 365 account was expecting
- On a free Entra ID account, apparently you cannot change the domain name of the tenant
- I had to sign up for Entra ID again using the same myname@something.onmicrosoft.com domain used by my MS 365 trial

# Microsoft 365
## Add User
Sign on to admin.microsoft.com with your admin credentials

At the very top you can hit the button to add users

![365_Add_user](https://github.com/user-attachments/assets/c9b69a8f-2f2d-449c-b933-a52d86823bd4)

![365_Add_user2](https://github.com/user-attachments/assets/7320d9f2-e6e4-4873-8b1f-4ad515804ec7)

At the prompt you can assign licenses like Microsoft 365

![365_Assign_License](https://github.com/user-attachments/assets/e80afc2e-c574-4338-8df1-e304d31f85df)

For roles you can choose whether the user has extra privalages like Admin rights:

![365_Assign_Role](https://github.com/user-attachments/assets/363b8c10-431b-4804-bf9a-4f4591cc72a5)

Hit Finish and you're done

![365_Add_User_Finish](https://github.com/user-attachments/assets/dcf63765-c82e-4001-a454-6a6f92004b3e)

## Reset Password

Sign on to admin.microsoft.com with your admin credentials

Check the User you want to reset the password for

At the very top you can hit Reset Password

![365_Reset_Password1](https://github.com/user-attachments/assets/6a29c223-a477-4114-a68a-73c3b856bdcb)

If you choose to automatically create password make sure you write it down

You can additionally have the user reset it when they sign on next

![365_Reset_Password2](https://github.com/user-attachments/assets/707eb99f-0825-403c-b28e-f89d1844b4f0)

![365_sign_in](https://github.com/user-attachments/assets/99de98ca-adaa-40dc-a859-83443d708ce8)

![365_Reset_Password3](https://github.com/user-attachments/assets/de0b7763-695f-48cc-9456-51bee2449d0e)


# Entra ID
## Joining Windows 10 to Entra ID
I set up a Windows 10 Pro client using Virtualbox

The VM has 2 CPU cores, 8 gigs of RAM, 50 gigs of virtual HD, one Network Adapter set to NAT

Login to the machine with local admin account

![settings](https://github.com/user-attachments/assets/30ecf4df-f647-4f0f-a13e-6577a5024bda)

Go to settings > Accounts
![Accounts](https://github.com/user-attachments/assets/2f9a0ef2-9611-4743-a039-2d4cb2344147)

Hit Access Work or School

![Access_Work_School](https://github.com/user-attachments/assets/0cc327b9-1e15-4966-99be-8830cd40fc78)

Here you can join Entra ID.  

![Join_Entra](https://github.com/user-attachments/assets/ae51ec50-e954-4241-90a3-527c5ad102c3)

You will need to input the credentials of an account already in Entra ID.  

I used my @something.onmicrosoft.com account that I created when I signed up for MS 365

![Join_Entra2](https://github.com/user-attachments/assets/bef63694-4b0e-4179-9e37-57e55f3065c6)

You can now login with an Entra ID account
![Entra_ID_login](https://github.com/user-attachments/assets/f722481c-2a62-4c70-97dd-7d61dc85f97e)

You will be required to provide two factor authentication so you will need Microsoft Authenticator on your phone

![Entra_ID_login2](https://github.com/user-attachments/assets/7d2bc687-b457-4abd-bc27-38f8049eb55a)

![Entra_ID_login3](https://github.com/user-attachments/assets/588e597c-3bd1-43cf-80f0-4d2d77ddec8e)

![Entra_ID_login4](https://github.com/user-attachments/assets/a2725608-63a8-4354-9b80-c608516727cd)


![Entra_ID_login5](https://github.com/user-attachments/assets/ebedf021-6f47-4048-9ab9-6e14fce69311)

You will also need to create a PIN

![Entra_ID_login6](https://github.com/user-attachments/assets/f1b783aa-7e8a-413e-9fee-40688ac511df)

# Intune

## Install App 

After we join a Windows 10 machine to Entra ID, it'll be available in Intune.

Login to intune.microsoft.com with admin credentials

From the Admin Center go to Devices, you should see the machine we joined to Entra ID:

![Intune_Devices](https://github.com/user-attachments/assets/19927fea-206d-42c4-a13b-4bae71ec910e)
![Intune_Devices_2](https://github.com/user-attachments/assets/2c29fda8-e926-4a97-bc9d-052af7cb896d)
![Intune_Devices_3](https://github.com/user-attachments/assets/d279e21c-fa55-41ab-9a6d-25941d12f028)

Using Intune we can deploy an app to the machine.

Go to Apps

![Intune_App](https://github.com/user-attachments/assets/88e56b45-577a-4f97-aaf5-64f2cd3cad19)

Select Windows Apps and hit Add

![Intune_App_Add](https://github.com/user-attachments/assets/75819dae-d5cb-4d96-9010-4e6602460038)

Choose Microsoft 365 for Windows 10 and later

![Intune_App_Add_365](https://github.com/user-attachments/assets/df8aa76c-3acc-4d85-9921-90164fb5bac6)
![Intune_App_Add_365_2](https://github.com/user-attachments/assets/0c60b6a3-e84c-412e-aa6d-1e7f1e39e2f4)

I selected all the default apps since I'm sure they're included in my trial of Microsoft 365 Business premium 

Under properties I think Business Premium license includes "Use shared computer activation" but I selected No

![Intune_App_Add_365_3](https://github.com/user-attachments/assets/270b8c02-cf4c-4516-aa45-18890a3b8a85)

For Assignments I added the group I created when I signed up for MS 365.  This is the business name I used when I signed up for MS 365, which defaulted as the tenant when I signed up for Entra ID.

![Intune_App_Add_365_4](https://github.com/user-attachments/assets/192e27de-f0b8-4268-a3fe-c575aba56c42)
![Intune_App_Add_365_5](https://github.com/user-attachments/assets/efa9576d-1720-4c0a-ae5f-113146ed7775)

Hit create

![Intune_App_Add_365_6](https://github.com/user-attachments/assets/49c14a80-6b9d-441d-9e77-8c2a0d8ab224)

Log back into the Windows 10 machine with Microsfot 365 user we created earlier

Apparently you have to wait for the machine to connect to Intune before it downloads

I waited on the desktop for about 15 minutes before the Microsoft Office 365 apps began showing up on the start menu

![Intune_App_Add_365_7](https://github.com/user-attachments/assets/e685cbd0-0766-4430-b0a6-07efcbf001e3)








