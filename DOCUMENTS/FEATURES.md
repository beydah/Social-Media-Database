# Social Media Database Template (Free)

<div style="text-align: center;">
  <a href="https://github.com/beydah/Social-Media-Database">
   <img src="https://raw.githubusercontent.com/beydah/asset/main/button/home_off.png" style="width: 10%;"  alt="<< Return to Home Page <<">
  </a>
</div>

</br>

<div style="text-align:center;">
    <img src="https://i.imgur.com/waxVImv.png" alt="Colorful Stick">
</div>

## Database Features

- MDF File: File Type ROWS Data, Size 10MB, Autogrowth 50MB, Max Size Unlimited.
- LDF File: File Type LOG, Size 10MB, Autogrowth 50MB, Max Size Unlimited.

<div style="text-align:center;">
    <img src="https://i.imgur.com/waxVImv.png" alt="Colorful Stick">
</div>

## Table Features

- **dbo.Customer:** Contains data related to user profiles and customer information. To be filled by the user.
- **dbo.Request:** Represents relationships indicating users' follow requests to other users. To be filled by the user.

- **dbo.Follow:** Represents relationships showing users following other users. To be filled by the user.
- **dbo.Blocking:** Represents relationships indicating users blocking other users. To be filled by the user.

- **dbo.Content:** Contains data of shared content. To be filled by the user.
- **dbo.Comment:** Stores data of comments made by users. To be filled by the user.

- **dbo.Message:** Contains details of sent messages. To be filled by the user.
- **dbo.Conversation:** Contains data of conversations and messaging between users. Automatically populated.

- **dbo.Liked:** Stores data of content and comments liked by users. To be filled by the user.
- **dbo.Report:** Contains data of complaints and reports submitted by users. To be filled by the user.

- **dbo.Notification:** Contains data related to notifications sent to users. Automatically populated.
- **dbo.Settings:** Stores data of user account settings. To be filled by the user.

- **dbo.User Logs:** Contains data of user activities and login records. Automatically populated.
- **dbo.Cookies:** Contains data of user session information and cookie data. Automatically populated.

- **dbo.Blocking_Reason:** Stores data explaining the reasons behind blocking actions. To be filled by employees.
- **dbo.Report_Type:** Stores data of report types. To be filled by employees.

- **dbo.Language:** Contains data of language options used. To be filled by employees.
- **dbo.Location:** Stores data of location information. To be filled by the user.

- **dbo.Hashtag:** Contains data of tags added to content. To be filled by the user.
- **dbo.Hashtag_Category:** Stores data of tag categories. To be filled by employees.

- **dbo.Analytics:** Contains data of analysis results. Automatically populated.
- **dbo.Algorithm:** Contains data related to algorithms and processes used. Automatically populated.

- **dbo.Recommendation_Content:** Stores data of recommended content for users. Automatically populated.
- **dbo.Recommendation User:** Contains data of other users recommended to users. Automatically populated.

- **dbo.AD:** Represents the table containing advertisement data. To be filled by the customer.

<div style="text-align:center;">
    <img src="https://i.imgur.com/waxVImv.png" alt="Colorful Stick">
</div>

## Procedure Features

### STORED PROCEDURE FUNCTIONALITY
Stored procedures streamline the handling of frequently used records, 
updates, deletions, and selections, making operations more automated and straightforward.

- Enhanced security measures.
- Ability to receive parameters from external sources.
- Enables faster query execution.
- Automation of tasks.
- Reduction of complexity.

### 25 PROCEDURES FOR SOCIAL MEDIA
Below are the names of the planned procedures and their associated tables. 
None of them were made except the first one.

Example* = Mandatory fields are indicated with an asterisk.

Example! = Tables that have not been created or are not necessary are marked with an exclamation mark.

 1.  CREATE_USER		- Customer* + Settings* + User_Logs* + Algorithm* + Analytics*

 2.  CREATE_POST		- Content* + (UPDATE Customer* + Analytics* + Hashtag + Hashtag_Category)
 
 3.  CREATE_COMMENT		- Comment* + (UPDATE Content* + Notification* + Analytics* + Algorithm)
 
 4.  CREATE_LIKE		- Recommendation_Content* + Liked* + (UPDATE Content* + Algorithm* + Analytics*) 
 
 5.  CREATE_FOLLOW		- Recommendation_User* + Request* + Follow* + Blocking* + (UPDATE Customer*)
 
 6.  CREATE_MESSAGE		- Message* + Notification* + (HIBRIT Conversation*) + (UPDATE Algorithm* + Analytics)
  
 7.  DELETE_USER		- Customer* + Settings* + User_Logs* + Algorithm* + Analytics*
 
 8.  DELETE_POST		- Content* + (UPDATE Customer* + Analytics* + Hashtag + Hashtag_Category)
 
 9.  DELETE_COMMENT		- Comment* + (UPDATE Content* + Notification* + Analytics* + Algorithm)

10.  DELETE_LIKE		- Recommendation_Content* + Liked* + (UPDATE Content* + Algorithm* + Analytics*) 

11.  DELETE_FOLLOW		- Recommendation_User* + Request* + Follow* + Blocking* + (UPDATE Customer*)

12.  DELETE_MESSAGE		- Message* + Notification* + (HIBRIT Conversation*) + (UPDATE Algorithm* + Analytics)
 
13.  UPDATE_USER		- Customer* + Settings* + User_Logs* + Cookies + Analytics

14.  UPDATE_POST		- Content* + Hashtag + Hashtag_Category + Analytics + (DELETE Comment)

15.  UPDATE_COMMENT		- Comment* + Notification* + Hashtag + Hashtag_Category Kategori + Analytics

16.  UPDATE_MESSAGE		- Message* + Notification* + Conversation* + Algorithm + Analytics

17.  UPDATE_ANALYTICS	- Recommendation_User* + Recommendation_Content* + Recommendation_AD* + Algorithm* + Analytics*

18.  UPDATE_REPORT		- Report* + Blocking* + Blocking_Reason + Report_Type + Analytics*
 
19.  SELECT_PROFILE		- Customer* + Follow + Settings + Request + Blocking

20.  SELECT_CONTENTS	- Customer* + Content* + Liked* + Comment + Tagged_Users!

21.  SELECT_LIKES		- Customer* + Content* + Liked_Users!* + Liked_Content!* + Liked_Notification!

22.  SELECT_COMMENTS	- Content* + Comment_Users!* + Comment_Content!* + Comment_Liked!* + Comment_Reply!

23.  SELECT_MAIN		- Following!* + Following_Content!* + Recommendation_User* + Recommendation_Content*+ Recommendation_AD*

24.  SELECT_SEARCH		- Following_Users!* + Customer* + User_Common_Follower!* + Recommendation_Hashtag!* + Hashtag*

25.  SELECT_DISCOVER	- Recommendation_Content* + Recommended_Hashtag_Content!* + Recommended_Following_User_Post!* + Recommendation_AD!* + AD

</br>

<div style="text-align:center;">
    <img src="https://i.imgur.com/waxVImv.png" alt="Colorful Stick">
</div>

</br>

<div style="text-align: center;">
  <a href="#social-media-database-template-free">
    <img src="https://raw.githubusercontent.com/beydah/asset/main/button/scroll_off.png" style="width: 15%;"  alt="^ Scroll UP ^">
  </a>
  <a href="https://github.com/beydah/Social-Media-Database/blob/main/DOCUMENTS/INSTALLATION.md">
    <img src="https://raw.githubusercontent.com/beydah/asset/main/button/next_on.png" style="width: 15%;"  alt=">> Continue Reading >>">
  </a>
</div>
