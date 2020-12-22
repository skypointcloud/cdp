# SkyPoint Cloud Bot(Preview)

Connect with Microsoft Teams to interact with our bot in order to gather relevant information regarding customer profiles from our platform.

<!-- ![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/bot.PNG?raw=true) -->

## Prerequisites

In order to set up and configure the bot, there are certain requirements that needs to be fulfilled:
1. There's at least one data source added.
2. The Stitch process is complete.
3. Fields are added to the search and filter index.

## Functionalities offered by the SkyPoint Cloud bot

The bot provides lookup capabilities for customer profiles.

### Login
1. The first and foremost action required from a user to avail all the functionalities of our bot is to **LOGIN**.
2. Type **Login** and click enter. The bot will send you a card containing a **Sign In** button.
![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/loginstep1.PNG?raw=true)

3. On clicking the Sign In button, you will be requested to enter your credentials for a successful login. Once that is complete, the bot will respond with a message suggesting the same.
4. Also, with the successful login message, you will recieve a **list of tenants** that you are a member of, and the bot will request you to specify which tenant you would like to connect to. If there is only a single tenant of which you are a member of, then by default, that tenant will be selected and you will then move forward to the next step.
5. In case of multiple tenants, you can select the specific tenant by either typing the ***name*** of that tenant or the ***serial number*** of that tenant from the list presented to you by our bot.
6. After selecting a specific tenant, the bot will respond with another list containing the names of the instances owned in that particular tenant.
7. You can choose a specific instance by either typing the name of the instance or the serial number of the instance from the list presented to you by our bot.
8. Post that, you are now successfully logged in and can extract valuable information regarding customer profiles present in that specific instance of that specific tenant.

### Switch Tenant
1. In order to switch tenant, the only requirement needed is that you have logged in.
2. Moving forward, to switch to a particular tenant, you can type **switchtenant** and the bot will present you a list of all the tenants that you are a member of.
3. You can choose a specific tenant by either typing the name of the tenant or the serial number of the tenant from the list presented to you by our bot.
4. After selecting a specific tenant, the bot will respond with another list containing the names of the instances owned in that particular tenant.
7. You can choose a specific instance by either typing the name of the instance or the serial number of the instance from the list presented to you by our bot.

### Switch Instance
1. In order to switch instance, the only requirement needed is that you have logged.
2. Moving forward, to switch to a particular instance, you can type **switchinstance** and the bot will present you a list of all the instances that you are a member of.
3. If there is only one instance, then the bot will respond by notifying you about it and then that single instance will be selected by default.
3. In case of multiple instances, the bot will respond with another list containing the names of the instances owned in that particular tenant.
7. You can choose a specific instance by either typing the name of the instance or the serial number of the instance from the list presented to you by our bot.

### Search
1. In order to search for a particular customer profile, you must have logged in to a particular tenant and selected a particular instance where the customer profiles are present.
2. To search for a particular customer profile, enter **Search** followed by a name, email address, or any other field on the customer profile that is added to the search and filter index.
3. Post search, you will get a list of possible results presented in a pageful manner out of which the user gets to decide and choose the specific customer which he/she would be looking for. In case of a single match, the bot will respond you with a card with up to 15 fields from the resulting customer profile.
4. In case of multiple matches, on choosing the specific customer from the list, you'll get a card with up to 15 fields from the resulting customer profile.

### Help
In order to know about all the possible functionalities, you can type **Help** and the bot will respond with a list of all the functionalities with a brief description to each of them.

![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/bothelp.PNG?raw=true)

### Logout
To logout, just type **logout** and you will be logged out from the session and the bot will notify you the same.