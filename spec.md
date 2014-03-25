---
tags: test
---

# User Collections Design Spec

[Overview](#overview)

[Success Metrics](#successmetrics)

[User Collection Features](#usercollectionfeatures)

[User Stories](#userstories)

[Specs](#specs)

## <a name="overview">Overview</a>

### What are user collections?

User collections allow Marketplace community members to create collections of apps for themselves, to share with friends and family and to share with the Marketplace community.

### User problem

Both consuming and creating collections improves the Marketplace experience for users.

**Why users want to consume collections**

*Discovery*. People want help finding great apps that are relevant to their interests and locale. Collections highlight the best apps. 

**Why users want to create collections**
* *Saving apps for later installation*. People want to be able to save apps for later. They might be on data and want to save an app to download later when they have a wifi connection. Or a user might be deciding between many different types of apps and wants to bookmark them and review them before selecting one and downloading it.
* *Sharing with friends*. People want to help their friends find cool apps. 
* *Sharing with the community*. People want to share their expertise of apps with others. 

### Business problem

User collections allow the Markeplace to scale content in the feed and help identify locally relevant content.

* *Scale*. Firefox Marketplace will always have a limited paid editorial staff. We need community members to create compelling content for Marketplace users to consume.
* *Local Content*. Firefox Marketplace needs to show locally relevant content. We need community members in each region to create locally relevant content for users to consume. 

### Target Audience

While user collections can be used by everyone on the Marketplace we believe that the average user and power users will use them in different ways. 

**Average user will:**
* Consume collections to discovery new apps
* Add apps to the App Wishlist to download later

**Power users will:**
* Create new collections.
* Share collections with friends & family.
* Create collections to share with the community.

### User Research

We conducted multiple usability studies of user collections on mobile and desktop. 

**User Collections Mobile Prototype 1** 

Study conducted on UserTesting.com on December 18, 2013

* *Purpose of Study*: Evaluate the experience and user understanding of creating a group of apps and sharing the group with the Marketplace community. The test will identify pain points with the user flow and usefulness of user collections. We also want to get feedback on potential names for the feature (collections, lists, etc.)
* *Prototype tested*: [http://people.mozilla.org/~mhanratty/user_collections_prototype_v1/home.html](http://people.mozilla.org/~mhanratty/user_collections_prototype_v1/home.html)
* *Key takeways*:
    * Flow of creating groups, adding an app to a group and sharing the group made sense to participants
    * People had difficulty disambiguating between "Share" and "Share with the Community." 
    * Participants did not come up with a consistent name for the feature
    * Participants talked about this feature in regards to organizing apps on their device 
* Test results report: [https://docs.google.com/a/mozilla.com/document/d/10eGrgyuM2wRjPcfe49nA_OsQx9e1tPQwPcL028D1lzc/edit](https://docs.google.com/a/mozilla.com/document/d/10eGrgyuM2wRjPcfe49nA_OsQx9e1tPQwPcL028D1lzc/edit)

**User Collections Desktop Prototype 1** 

Study conducted on UserTesting.com on Febuary 06, 2014

* *Purpose of Study*: Evaluate the experience and user understanding of creating a group of apps and sharing the group with the Marketplace community on the desktop. The test will identify pain points with the user flow and discoverability of user collections. We also want to get feedback on potential names for the feature (collections, lists, etc.).
* *Prototype tested*: [http://people.mozilla.org/~mhanratty/User_Collections_Desktop_Prototype_02042014/home.html](http://people.mozilla.org/~mhanratty/User_Collections_Desktop_Prototype_02042014/home.html)
* *Key takeways*:
    * Flow of creating groups, adding an app to a group and sharing the group made sense to participants.
    * People had difficulty finding the feature.
    * Participants preferred the name “collections” for the feature
    * Participants had difficulty finding the bottom toolbar to make the list public.
* Test results report: [https://docs.google.com/document/d/15mKGX52-weGQXV7USfBzickyko83x0QZvSGjxQC4vAU/edit?usp=sharing](https://docs.google.com/document/d/15mKGX52-weGQXV7USfBzickyko83x0QZvSGjxQC4vAU/edit?usp=sharing)

## <a name="successmetrics">Success Metrics</a>
* User collections should increase successful app installs on Firefox OS by 5%.
* Other success metrics TBD by David Bialer

## <a name="usercollectionfeatures">User Collection Features</a>

**Collection Types**
* *App Wishlist*. The app wish list is a collection that every user has by default. The app wish list allows the user to save apps to install later or on another device and is intended for personal use. 
* *Custom Collections*. Custom collections are all other collections that a user creates themselves. These collections can be shared with the Marketplace community.

**Collection Elements**

App Wishlist
* graphic 
* avatar of the user who created the collection
* collection title "My App Wishlist"
* app (app icon, name, developer, content rating, review rating, free button). 

Custom Collection
* auto-generated graphic 
* display name of user who created the collection
* avatar of the user who created the collection
* collection title
* collection description [optional] 
* app (app icon, name, developer, content rating, review rating, free button). 
    
**Collection Features**

App wish list features
* Ability to add apps from app details screen.
* Ability to remove apps.

Custom collection features for collection creator
* Ability to add apps.
* Ability to make collection visible to all of Marketplace or keep hidden.
* Ability to view statistics on a collection (shares, views, upvotes).
* Ability to remove apps.
* Arrange the order of apps.
* Ability to delete a collection.

Custom collection features for collection consumer
* Ability to share collection.
* Ability to upvote the collection.
* Ability to flag the collection for abuse.

**Collection Visibility**

Collections that are made public by their creators will be visible on the following screens
* "Community" screen accessible via top level navigation 
* As modules in the feed chosen by the editor
* Category screens (P2)
* Search result screens

Visibility rules
* A collection must have three or more apps to be publicly visible on the Marketplace
* If an app in a collection is not available in the user’s region, by the user’s operator, or on their device (mobile use case), the user will not see that app though they will be able to see the rest of the apps in the collection.
* If none or less than 3 of the apps in the collection are available in the user’s region, the user’s operator, or on their device (mobile use case) the user will not see that collection.
* Proposal: Precompute visible collections by the common device profiles so the filtering doesn't have to be done in real time.
 
Preventing/Handling spam and offensive content in visible collections
* Do not feature new collections prominently (i.e. on the homescreen.)  Make new collections available but only on community screen. Once the collection receives a good reputation (many views, many installs from views, likes, etc.) allow it to be featured on the home screen.
* Allow users to flag content for abuse. If collection receives 3 abuse flags remove it from "Community" screen.
* If a user posts a url in titles or description it should not be clickable. (main source of spam for AMO)
* Auto-flag suspicious collections that appear to be spam and have them added to a review queue
* Filter for users creating many, many collections (100s of collections)
* Filter for users frequency of collection making (100s of collection in small amount of time)
* Filter for duplicate collections (often spam bot)
* Create a black list of banned users


## <a name="userstories">User Stories</a>
### Mobile
* As a user I want to add an app to an existing collection from the app details screen [github issue](https://github.com/mhanratty/marketplaceux-usercollections/issues/9) | [spec for flow](#addappexistingcollection) | [spec for modal](#addappmodal)
* As a user I want to add an app to a new collection from the app details screen  [githhub issue](https://github.com/mhanratty/marketplaceux-usercollections/issues/10) | [spec for flow](#addappnewcollection) | [spec for modal](#addappmodal)
* As a user I want to create a new collection from the "Collections" screen [githhub issue](https://github.com/mhanratty/marketplaceux-usercollections/issues/11) | [spec for flow](#createcollection)  | [spec for create collection screen](#createcollectionviews)
* As a user I want to see a warning if I try to save a collection without a name (required) [spec](#collectionnamewarning)
* As a user I want to be able to remove an app from a collection [githhub issue](https://github.com/mhanratty/marketplaceux-usercollections/issues/13) | [spec](#removeapp)
* As a user I want to be able to delete a collection [githhub issue](https://github.com/mhanratty/marketplaceux-usercollections/issues/4) | [spec](#deletecollection)
* As a user I want to be able to customize the background of my collection graphic [githhub issue](https://github.com/mhanratty/marketplaceux-usercollections/issues/12)  | [spec](#changecollectionbackground)
* As a user I want to be able to edit my avatar and display name that appears on the collection [githhub issue](https://github.com/mhanratty/marketplaceux-usercollections/issues/18) | [spec](#editprofile)
* As a user I want a place where I can view all of my collections [githhub issue](https://github.com/mhanratty/marketplaceux-usercollections/issues/19) | [spec](#collectionsscreen)
* As a user I want an app wish list to store apps for later [githhub issue](https://github.com/mhanratty/marketplaceux-usercollections/issues/1) | [spec](#appwishlist)
* As a user I want to be able to see stats on my collections (number of shares, upvotes and views) | [spec](#collectionsscreen)
* As a user I want a dedicated place to view user collections on the Marketplace [github issue](https://github.com/mhanratty/marketplaceux-usercollections/issues/23) | [spec](#communityscreen)
* As a user I want to be able to report a collection for abuse [githhub issue](https://github.com/mhanratty/marketplaceux-usercollections/issues/27) | [spec](#reportcollection)

### Desktop
* As a user I want to view all of my collections on desktop [github issue](https://github.com/mhanratty/marketplaceux-usercollections/issues/28) | [spec](#collectionsscreendesktop)
* As a user I want to create a collection on desktop [github issue](https://github.com/mhanratty/marketplaceux-usercollections/issues/29) | [spec](#collectioncreatedesktop)
* As a user I want to view my collection on desktop [spec](#collectionviewdesktop)
* As a user I want to edit a collection on desktop [spec](#collectioneditdesktop)
* As a user I want a dedicated place to view user collections on the Marketplace on desktop [spec](#communityscreendesktop)

### Tablet
* As a user I want to view all of my collections on tablet [spec](#collectionscreentablet)
* As a user I want to create a collection on tablet [spec](#collectioncreatetablet)
* As a user I want to view my collection on tablet [spec](#collectionviewtablet)
* As a user I want to edit a collection on tablet [spec](#collectionedittablet)
* As a user I want a dedicated place to view user collection on the Marketplace on tablet. [spec](#communityscreentablet)

### Curation Tool
* As a curator I want to be able to view collections made by the community.
* As a curator I want to be able to publish user collections to the feed.

## <a name="specs">Specs</a>
<a name="addappexistingcollection">![he can see so much more](http://mhanratty.github.io/marketplaceux-usercollections/img/usercollections_addappexistingcollection.png)</a>

**Acceptance criteria for adding app to an existing collection**
* Icon to add an app to a collection appears on the app details screen.
* A modal should open when user selects icon to add app to a collection.
* If there is only one collection, that collection should be selected.
* The user should have the ability to create a new collection.
* When an app has been added to a collection, a confirmation should appear with the icon of the app, the name of the app, and the name of the collection it was added to.
* In the confirmation screen the name of the collection should link to that collection's landing screen.
* When the user dismisses the confirmation message the user should return to the app details screen.

<a name="addappnewcollection">![he can see so much more](http://mhanratty.github.io/marketplaceux-usercollections/img/usercollections_addappnewcollection.png)</a>

**Acceptance criteria for adding an app to a new collection**
* When the user selects create a new collection the user should be taken to a new screen.
* Entering a name for the collection is required. The "Create" button should be disabled until the user has created the collection name.
* When the user hits enter on the collection name field they should automatically be taken to the description field.
* Entering a description for the collection is optional. 
* If the user hits enter on the description field the keyboard should dismiss.
* The user can choose whether to make the collection visible for others to view on the Marketplace. Making the collection visible should be selected by default.
* When the user selects "Create" the user should return to the add to collection screen. The collection they just created should be listed directly after the app wishlist and it should be selected.
* The user can select additional collections to add the app to.

<a name="addappmodal">![he can see so much more](http://mhanratty.github.io/marketplaceux-usercollections/img/usercollections_addappmodal.png)</a>

**Acceptance criteria for the add to collection modal**
* The collections should be listed with "The App Wishlist" always on top by default. Other collections should be listed in reverse chronological order from newest to oldest.
* All collections should include the number of apps currently in the collection.
* If the user only has one collection (the app wishlist) that collection should be selected.
* If the user has more than one collection than no collections should be selected by default.
* If no collection is selected the "Ok" button should be deactivated.
* The entire collection line item should be a touch target
* The app may be added to multiple collections.
* If there are 3+ collections a scroll bar should appear.

<a name="createcollection">![he can see so much more](http://mhanratty.github.io/marketplaceux-usercollections/img/usercollections_createcollectionfromcollections.png)</a>

**Acceptance criteria for creating a collection from the collections screen**
* There should be a prominent call to action for the user to create a new collection. When selected this call-to-action should take the user to the create collection screen.
* Create collection screen
    * The create collection screen should have a "Done" link when the user is finished creating their collection.
    * The create collection screen should show a default graphic for the collection. 
    * The user's current Markeplace avatar should be visible on the graphic.
    * The user's current Marketplace display name should be visilble on the graphic.
    * Entering a name for the collection is required. 
    * When the user enters the name of the collection, it should show up in real time on the graphic above the user's display name.
    * When the user hits enter on the collection name field they should automatically be taken to the description field.
    * If the user hits enter on the description field the keyboard should dismiss.
    * There should be a call-to-action button that allows users to add apps to the collection. The add apps call to action should always appear after the "Make visible" toggle and before any apps on the create/edit collection screen.
    * When the user selects the add to apps call-to-action a new screen should appear for the user to search for apps.
* Add to apps screen
    * On the add to apps screen there should be a search box for users to search for an app by name in the Marketplace. 
    * On add to apps screen the search box should only return mobile apps available for that user's region and operator.
    * The user must click enter to execute the search.
    * Search results should appear with their icon, app name, developer name, content rating and review rating. Instead of an install button the listing should have a grey circle indicating the ability for the app to be selected.
    * The entire line item for the app is a touch target that will select the app.
    * When the app is selected, the icon should appear selected. 
    * After x seconds the app listing should fade to white. A message "App add to collection" should appear and remain for x seconds after which the entire listing should disappear.
    * The user can select multiple apps from the search results to add to the collection.
    * The user can delete their current search and execute multiple searches adding multiple apps.
    * When user selects "Done" on add to apps screen the user should return to the create collection screen.
* Create collections screen after an app is added
    * If at least one app is selected the background of the graphic should change from grey to a color. 
    * Any apps that have been added should show up as icons on the graphic. The first app added should be added as the center app. The second app added should be in the 2nd slot (slot to the left of the center slot). The 3rd app added should be in the 4th slot (slot to the right of the center slot. The 4th app should be added to the 1st slot and the 5th app should be in 5th and final slot.
    * Once a user adds an app an icon should appear allowing the user to change the background of the collection. The background color/graphic should be randomly generated.
    * If the user selects "Done" and the collection requirements are fulfilled (the collection has a name) the user is taken to the collection landing screen.
    * If the user selects "Done" and the user has added a description or an app but has not created a name, the user should see a warning scree (see [spec](#collectionnamewarning))
    * If the user selects "Done" and has not inputted any data (no name, description, or apps) no collection is created. The user should be taken back to the "Collections" screen.

<a name="createcollectionviews">![he can see so much more](http://mhanratty.github.io/marketplaceux-usercollections/img/usercollections_createcollectionviews.png)</a>

**Acceptance criteria for create collections screens**
* The create collection screen should have a "Done" link when the user is finished creating their collection.
* The create collection screen should show a default graphic for the collection that is grey with slots for icons for apps that are added.
* The user's current Markeplace avatar should be visible on the graphic. 
* The user's current Marketplace display name should be visible on the graphic.
* The user should be able to click on the avatar and be taken to their profile to edit their avatar and display name.
* Entering a name for the collection is required. 
* Entering a description for the collection is optional. 
* Adding an app to a collection is optional.
* The user can choose whether to make the collection visible for others to view on the Marketplace. Making the collection visible should be selected by default.
* There should be a call-to-action button that allows users to add apps to the collection. The add apps call to action should always appear after the "Make visible" toggle and before any apps on the create/edit collection screen.
* The user should be able to delete a collection. The button for deleting a collection should always appear at the bottom.
* Once a user adds an app an icon should appear allowing the user to change the background of the collection. This background should be randomly generated.
* Any apps that have been added should show up as icons on the graphic. The first app added should be added as the center app. The second app added should be in the 2nd slot (slot to the left of the center slot). The 3rd app added should be in the 4th slot (slot to the right of the center slot. The 4th app should be added to the 1st slot and the 5th app should be in 5th and final slot.
* Apps should be listed underneath the add apps call-to-action. 
* App listing should have a remove icon and icon that indicates that listing can be moved up in down in order.

<a name="collectionnamewarning">![he can see so much more](http://mhanratty.github.io/marketplaceux-usercollections/img/usercollections_collectionnamewarning.png)</a>

**Acceptance criteria for collection name warning**
* When a user selects "Done" and the collection has description or added app (or both) without a name this warning should appear (if the collection has no data, do not show this warning and just take user back to the previous screen.)
* The user should be able to decide whether to name the collection to save or not to save it. 
* If the user chooses not to save the collection, take the user back to the previous screen she was on. 
* If the user chooses to name her collection, take her to the name field. The cursor should be in the name field and the keyboard up (on mobile) so the user can immediately type in a name.


<a name="removeapp">![he can see so much more](http://mhanratty.github.io/marketplaceux-usercollections/img/usercollections_removeapp.png)</a>

**Acceptance criteria for removing an app from a collection**
* There should be an icon to remove the app from the collection.
* After x seconds the app listing should fade to white. A message "App removed from collection" should appear and remain for x seconds.
* After x seconds the apps below should animate up into the space the app that was removed once occupied.

<a name="deletecollection">![he can see so much more](http://mhanratty.github.io/marketplaceux-usercollections/img/usercollections_deletecollection.png)</a>

**Acceptance criteria for deleting a collection**
* The delete collection button should always be at the bottom of the collection.
* The user must confirm that the collection should be deleted.
* If the user delete's the collection she should return to the Collections screen where she will see feedback that the collection was successfully deleted. 

<a name="changecollectionbackground">![he can see so much more](http://mhanratty.github.io/marketplaceux-usercollections/img/usercollections_changecollectionbackground.png)</a>

**Acceptance criteria for changing the background of a collection**
* The user can only change the background of a collection if at least 1 app is added to the collection
* The user clicks an icon in the upper right corner to access the choose background selector.
* The current color/pattern combination should be selected in the choose background screen.
* When user hits done she is taken back to create collection screen where the new color pattern combination has been applied to the graphic.

<a name="editprofile">![he can see so much more](http://mhanratty.github.io/marketplaceux-usercollections/img/usercollections_editprofile.png)</a>

**Acceptance criteria for editing the avatar and display name for a collection**
* Selecting the user's avatar will take the user to the edit profile screen.
* To edit the avatar the user selects the avatar. The devices gallery app should open. The user can select a profile image from their gallery.
* The new avatar should be displayed when the user returns to the edit profile screen.
* When user selects done she returns to the create collection or edit collection screen with her new avatar displayed.

<a name="collectionsscreen">![he can see so much more](http://mhanratty.github.io/marketplaceux-usercollections/img/usercollections_collectionsscreen.png)</a>

**Acceptance criteria for collections screen**
* The collections screen is in under the main navigation item "Apps and Collections" under a tab labeled "Collections."
* The app wishlist is in under the main navigation item "Apps and Collections" under a tab labeled "Wishlist." 
* If the user has no custom collections show a message about collections directly above the create new collection call to action
* The create collection call-to-action should appear above the list of collections
* Collections should we listed in reverse chronological order from newest to oldest.
* The collection creator should be able to view the stats for their collection including number of shares, number of views and number of upvotes.
* If the user has more than 3 collections she should be able to search through her collections. The search box should only appear if the user has 3 or more collections.
* The search box should appear just above the list of collections.

<a name="appwishlist">![he can see so much more](http://mhanratty.github.io/marketplaceux-usercollections/img/usercollections_appwishlist.png)</a>

**Acceptance criteria for my app wish list**
* If the user has no apps in their wishlist they should view a message telling them how to add apps to their wishlist using the "+" icon on the app details screen
* The apps in the wish list should be listed in reverse chronological order from newest app added to oldest app added.
* The user should be able to edit their wish list. 
* In edit mode the user should be able to remove apps from the list by clicking the remove icon on the app listing.
* If an app on the wish list is installed by the user the app should be automatically removed from the user's app wishlist.

<a name="communityscreen">![he can see so much more](http://mhanratty.github.io/marketplaceux-usercollections/img/usercollections_communityscreen.png)</a>

**Acceptance criteria for the community screen**
* "Community" is a main navigation item listed after "Categories"
* User's can toggle between viewing user collections listed in order of most popular and new.
* By default the user should view the most popular order of collections
* Only show user collections that have 3 or more apps
* If none of the apps in the collection are available in the user's region, the user's operator, or on their device (mobile use case) the user should not see that collection.
* If an app in a collection is not available in the user's region, by the user's operator, or on their device (mobile use case), the user will not see that app though they will be able to see the rest of the apps in the collection
* The user should be able to share a collection.
* The user should be able to upvote a collection.

<a name="reportcollection">![he can see so much more](http://mhanratty.github.io/marketplaceux-usercollections/img/usercollections_reportcollection.png)</a>

**Acceptance criteria for flagging a collection for abuse**
* There should be an icon on the collection landing screen that allows the user to report a collection. 
* The creator of a collection should not be able to report their own collection.
* When the report icon has been selected, an overlay should appear asking for the reason for the report. The three options are: spam, inappropriate language, and inappropriate avatar.
* After the user has selected the reason for reporting the collection the user should return to the collection landing screen and view feedback that the collection was reported.

<a name="collectionsscreendesktop">![he can see so much more](http://mhanratty.github.io/marketplaceux-usercollections/img/usercollections_collectionsscreendesktop.png)</a>

**Acceptance criteria for viewing all of your user collections on desktop**
* Collections are visible under “My Account” when the user is signed in. 
* On desktop the user can see Collections, Wishlist and My Apps in one view.
* On desktop the sections of the page have titles
* If there are > 3 collections show a search bar so that the user can search through their collections.
* Create new collection call-to-action should take user to the create a collection screen.
* Collections are listed from most recently created to oldest in blocks of 6 moving left to right, up to down. 
* The collection graphic should be the same as seen on mobile.
* If the user has > 6 collections the collections should start being visible as overflow content. A right arrow control should allow the user to scroll through the overflow content.
* If the user has 0 collections show text to let the user know what collections are. 

<a name="collectioncreatedesktop">![he can see so much more](http://mhanratty.github.io/marketplaceux-usercollections/img/usercollections_collectioncreatedesktop.png)</a>

**Acceptance criteria for creating a user collection on desktop**
* The user should view this screen when she clicks on "Create collection."
* The name of the collection is required. 
* When the user clicks on the "Name of collection" field she should be able to enter text. 
* If the user hits the enter or tab button while editing the name field take the user to the "Add description" field.
* The description field is optional. It should float to the right of the collection graphic.
* The graphic should be 6 columns and 264px tall on desktop.
* The user should be able to edit her profile. If the user clicks on their avatar on the collection graphic, take the user to the edit profile screen.
* The user should be able to edit the background of a collection. If the user clicks on the edit background icon the change background screen should open in a modal.
* The user should be able to decide whether to make a collection visible on dektop. By default the collection should be visible.
* The user should be able to search for apps via a search box on desktop.
* The user can search by an app name or the url of the app on Marketplace.
* The user should be able to clear a search using the "x" icon in the search box.
* After the user has entered a search the user should be able to filter their app search by all devices, desktop or mobile. By default it should filter by all devices.
* Search results should appear below the search bar. The result should have the app icon, app name and a call-to-action to add the app to a collection.
* The entire line item for the app is a touch target that will select the app.
* When the app is selected, the icon should appear selected. 
* After x seconds the app listing should fade to white. A message "App add to collection" should appear and remain for x seconds after which the entire listing should disappear (see how apps are added on the [spec for creating a collection](#createcollection)
* The user can select multiple apps from the search results to add to the collection.
* Add apps in 3 columns. The most recently added app should appear first in the list. 
* The "Cancel" and "Done" buttons should appear on the same level as the name of collection field.
* If the user selects "Cancel" take the user back to the screen she was previously viewing.
* If the user selects "Done" and the user has entered a collection name take the user to the collection landing screen.
* If the user selects "Done" and has not entered a collection name show the user a warning that the collection needs a name to be saved (see [spec](#collectionnamewarning))

<a name="collectionviewdesktop">![he can see so much more](http://mhanratty.github.io/marketplaceux-usercollections/img/usercollections_collectionviewdesktop.png)</a>

**Acceptance criteria for viewing a user collection on desktop**
* The collection should have a name.
* The collection should have an edit button if the user is the creator of the collection. The edit button should appear on the same level as the name of the collection field.
* If the user selects "Edit" take the user to the edit collection screen.
* The graphic should be 6 columns and 264px tall on desktop.
* If the collection does not have a description center the collection graphic in the center of the screen.
* If the collection has a description, make the graphic flush left with the collection name and float the description to the right of the graphic.
* Show 3 columns of apps. 
* Apps should be listed in reverse chronological order from newest to oldest. Apps should be listed in this order from right to left, up to down.

<a name="collectioneditdesktop">![he can see so much more](http://mhanratty.github.io/marketplaceux-usercollections/img/usercollections_collectioneditdesktop.png)</a>

**Acceptance criteria for editing a user collection on desktop**
* The user should view this screen when she clicks "Edit" on the collection landing screen.
* The name of the collection is required. 
* When the user clicks on the "Name of collection" field she should be able to enter text. 
* If the user hits the enter or tab button while editing the name field take the user to the "Add description" field.
* The description field is optional. It should float to the right of the collection graphic.
* The graphic should be 6 columns and 264px tall on desktop.
* The user should be able to edit her profile. If the user clicks on their avatar on the collection graphic, take the user to the edit profile screen.
* The user should be able to edit the background of a collection. If the user clicks on the edit background icon the change background screen should open in a modal.
* The user should be able to decide whether to make a collection visible on dektop. By default the collection should be visible.
* The user should be able to search for apps via a search box on desktop.
* The user can search by an app name or the url of the app on Marketplace.
* The user should be able to clear a search using the "x" icon in the search box.
* After the user has entered a search the user should be able to filter their app search by all devices, desktop or mobile. By default it should filter by all devices.
* Search results should appear below the search bar. The result should have the app icon, app name and a call-to-action to add the app to a collection.
* The entire line item for the app is a touch target that will select the app.
* When the app is selected, the icon should appear selected. 
* After x seconds the app listing should fade to white. A message "App add to collection" should appear and remain for x seconds after which the entire listing should disappear (see how apps are added on the [spec for creating a collection](#createcollection))
* The user can select multiple apps from the search results to add to the collection.
* Add apps in 3 columns. The most recently added app should appear first in the list. 
* The apps should show a control to allow the user to move apps in order.
* The apps should have a "x" icon so they can be removed. For remove interactions see [spec for removing an app](#removeapp) 
* The "Done" and "Delete collection" buttons should appear on the same level as the name of the collection field.
* If the user selects "Delete collection" require a confirmation. If the user confirms, take the user back to the collections screen with feedback that the collection was deleted (see [spec for deleting a collection](#deletecollection)) 
* If the user selects "Done" and the user has entered a collection name take the user to the collection landing screen.
* If the user selects "Done" and has not entered a collection name show the user a warning that the collection needs a name to be saved (see...)

<a name="communityscreendesktop">![he can see so much more](http://mhanratty.github.io/marketplaceux-usercollections/img/usercollections_communityscreendesktop.png)</a>

**Acceptance criteria for the community screen on desktop**
* Users Collections are visible under the “Community” tab in the main navigation
* Only user collections that follow the visibility rules will be shown.
* On desktop the sections of the page have titles
* By default collections should be sorted by popular. The user can also sort collections by “new.”
* The create new collection call-to-action will take user to the create a collection screen.
* Collections are listed from most recently created to oldest in blocks of 5 moving left to right, up to down. The collection graphic is sometimes mobile size (4 columns wide) and sometimes desktop sized (6 columns wide)
* A right arrow control should allow the user to scroll through the overflow content.

#### Viewing all of my user collections on tablet

<a name="collectionscreentablet">![he can see so much more](http://mhanratty.github.io/marketplaceux-usercollections/img/usercollections_collectionscreentablet.png)</a>

**Acceptance criteria for creating a collection on tablet**

Same as for desktop except...
* Collection search is below Collection title
* Only 4 collections are visible at a time

#### Creating a user collection on tablet

<a name="collectioncreatetablet">![he can see so much more](http://mhanratty.github.io/marketplaceux-usercollections/img/usercollections_collectioncreatetablet.png)</a>

**Acceptance criteria for creating a collection on tablet**

Same as for desktop except...
* "Cancel" and "Done" should appear above the name of the collection.
* The description field should appear below the graphic.
* Apps should appear in two columns.

#### User collection landing screen on tablet

<a name="collectionviewtablet">![he can see so much more](http://mhanratty.github.io/marketplaceux-usercollections/img/usercollections_collectionviewtablet.png)</a>

**Acceptance criteria for viewing a collection on tablet**

Same as for desktop except...
* "Edit" button should appear above the name of the collection.
* The description field should appear below the graphic.
* Apps should appear in two columns.

#### Editing a user collection on tablet

<a name="collectionedittablet">![he can see so much more](http://mhanratty.github.io/marketplaceux-usercollections/img/usercollections_collectionedittablet.png)</a>

**Acceptance criteria for editing a collection on tablet**

Same as for desktop except...
* "Delete collection" and "Done" should appear above the name of the collection.
* The description field should appear below the graphic.
* Apps should appear in two columns.

#### Community screen on tablet

<a name="communityscreentablet">![he can see so much more](http://mhanratty.github.io/marketplaceux-usercollections/img/usercollections_communityscreentablet.png)</a>

**Acceptance criteria for community screen on tablet**

Same as for desktop except...
* Only 4 collections are shown at a time.
* The collection graphic is always 4 columns wide.
