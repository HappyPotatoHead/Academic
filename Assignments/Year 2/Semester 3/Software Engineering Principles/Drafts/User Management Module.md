> [!INFO] Perspective
> I'll take the perspective of ordinary delivery system user.

**What, Why, How, When**

_Start from the top_
To use a delivery system, one must become the member or simply put, register an account. It's the basis of any app.

So, the first component of user management module is login/registering of account

# Login/Register User account

When a user starts up the app (_assuming the user has not loaded up the app before_), the user will be prompted to either login or register.

## Login

The user just inserts their email and password. If successful, the user logs in. If not, the user tries again.

## Register User Account

The user does not have an account. The user would insert the necessary personal details and password. The system would check if the email has already existed. If it has, the details are rejected, if not, the new user is added to the database.

![[login_module.png]]

## Options

![[User Management Module.png]]

### User's personal details

User can view their personal detail in this system. In the personal details page, user can view their chosen name, email, phone number, gender, and date of birth. If the user wishes to update their information, they can do so and provide the new information to each of the fields. When the new changes are saved, information of the user in the database is updated in conjunction. To the user, the process of updating personal information is quick and easy.

### Password and Security

If the user is concerned about their account security, they can head to the password and security page. They can turn on two-factor authentication if they have not already. Once turned on, the user will insert an alternate email address. After this, when logging in, a verification code will be sent to the user's email. The code is needed to complete the login

### Notification

The user can toggle receiving updates and information via email. This is done under a privacy policy that the system follows strictly.

### Deleting Account

When the user wishes to delete their account, they would receive an OTP code sent to their email for confirmation. Three attempts are given to the user to fill in the correct OTP. If the limit is exceeded, the user will be notified that there is an attempt made to delete their account via email. If the OTP is correct, the user will be lead to a page for them to provide us with feedback.

Once successful, the user information is deleted from the database.

### Payment Methods

The system supports payment via debit or credit, e-wallet, and cash-on-delivery. If the user wants to use debit or credit, they would insert their card information. If the user wants to use e-wallet, they would be brought to a page from their selected e-wallet for confirmation. Finally, if the user wishes to use neither, they can opt for the cash on delivery method. Once confirmed, their payment method will be updated in the database and used on their next purchase.

## New Changes

![[User Management Module-Page-3.drawio.png]]

## Question 1

The user management subsystem provides seven key functionalities: registration of a new user, login of an existing account, modification of users' account information, ensuring user accounts' security, toggling receiving notification via email, deleting user accounts, and modifying preferred payment methods. The main architecture used here is the Module View Controller architecture. This architecture creates clear separation of concerns between views, modules or controllers, and the database. There are multiple views being used, each tailored for respective functions. Additionally, some of the views use more than one controller or module or vice versa. For example, the removing account view uses both the **Feedback System** and the **Account Deletion Module**. The same example can also be used to emphasise loose coupling – the same view uses multiple modules.

When using the food ordering and transaction management system, users are required to log in with their username or email address and a password, given that they had already made an account. Otherwise, users are required to register for an account with their username, email address, password, and phone number. Optionally, the user can insert their gender as well as their date of birth.  This information is important to verify if the user is authentic the next time they log in. The additional, optional account information is meant for events that the user may be interested in.  

If the email address submitted has already existed, the user will be asked to provide an alternative email address. Once the account details have been submitted, a confirmation email will be sent to the user. Once the user confirms, the user will be inserted into the database and be directed to the login page; if not, the user’s account will not be created. Once logged in, the user will be shown the system’s homepage. To access the account management features, the user must navigate to the dedicated account management page.

On the account details page, users can view their inserted name, email, phone number, gender, and date of birth. If the user wishes to update their information, they can do so by providing new information to desired fields. When the new changes are saved, information of the user in the database is updated. To the user, the process of updating personal information is quick and easy. This is to ensure that the user gets a seamless and hassle-free experience.

To strengthen accounts’ security, an account security page is created to give users an option to enable two-factor authentication or change their passwords. When the two-factor authentication is enabled, the user will insert an alternate email address to receive a confirmation email. Once enabled, every time the user logs in, a verification code will be sent to the user's email, which is needed to complete the login. On the same page, users can change their passwords; they will have to provide their current password and a new password. When the user submits, the inserted current password will be verified against the database; if it exists, the process will shift to validating the new password; if not, the user’s request for a password change is denied. If successful, the new password is saved, and the user is logged out of the session.

If the user wishes to delete their account, they will receive an OTP code sent to their email for confirmation. Three attempts are given to the user to fill in the correct OTP. If the limit is exceeded, the user will be notified that there is an attempt made to delete their account via email. If the OTP is correct, the user will be led to a page for them to provide us with feedback. Once successful, the user information is deleted from the database.

The system supports payment via debit or credit, e-wallet, and cash-on-delivery. If the user wants to use debit or credit, they will insert their card information. If the user wants to use an e-wallet, they would be brought to a page from their selected e-wallet for confirmation. Finally, if the user wishes to use neither, they can opt for the cash on delivery method. Once confirmed, their payment method will be updated in the database and used on their next purchase.

## Question 4

To design my architectural solution, I have investigated multiple design patterns or techniques as well as architectural design to help guide me to create a robust yet efficient solution. The architectural design used in the user management system is Model-View-Controller or MVC architectural design. With this architectural design, a **clear separation of concern** in the components is created in the subsystem. This architecture improves **modularity and reusability**; each view or interface is independent and multiple views or interfaces can use the same modules or controllers. As a result, this architecture allows me to replace interfaces, controllers, and modules without worrying about affecting other components, **improving reliability and maintainability**. For instance, I can remake and replace the **Login Interface** without needing to replace the **Login Management Module**. This architecture **also emphasises loose coupling**, where each component is general enough to be reusable for other situations and uses. For example, the **Encryption System** is used for both account security function and account registration function.

A design pattern that is paired with MVC architectural design is the **modular design pattern**. The modular design pattern involves **breaking down a complex software into smaller, more manageable components**. For example, the account registration function involves several subfunctions or subsystems such as **Validate Registration Details**, **Email Service Module**, and **Encryption System**. This means that each function can be developed, maintained, and reused independently. Additionally, each of the subsystems can be broken down into more subsystems. Modular design lets me improve maintainability, scalability, testability, team collaboration, and reduced complexity when done properly and within specific boundaries.

I learnt that most software is written based on multiple architectural design and design patterns. Often times, architectural design patterns are paired with design patterns to take advantage of synergies or to complement the weaknesses of design patterns or architectural design patterns with strengths of another. For example, modular design pattern pairs well with MVC because both emphasise the importance of separation of concern and loose coupling, making the system more maintainable. Additionally, it also makes the system easier to be developed because each function is broken down into smaller subfunctions, allowing developers to focus on one function at a time.

