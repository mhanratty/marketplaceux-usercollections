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
* Sharecollections with friends & family.
* Create collections to share with community.

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
* 20%

## <a name="usercollectionfeatures">User Collection Features</a>

**Collection Types**
* *App Wishlist*. The app wish list is a default collection that every user has by default. The app wish list allows the user to save apps to install later or on another device and is intended for personal use. 
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
* Ability to delete a collection.

Custom collection features for collection consumer
* Ability to share collection.
* Ability to upvote the collection.
* Ability to flag the collection for abuse.

**Collection Visibility**

Collections that are made public by their creators will be visible on the following screens
* "Community" screen accessible via top level navigation 
* As modules in the feed chosen by the curator
* Category screens
* Search result screens

Visibility rules
* A collection must have three or more apps to be publicly visible on the Marketplace
* If an app in a collection is not available in the user’s region, by the user’s operator, or on their device (mobile use case), the user will not see that app though they will be able to see the rest of the apps in the collection.
* If none of the apps in the collection are available in the user’s region, the user’s operator, or on their device (mobile use case) the user in will not see that collection.
 
Preventing/Handling spam and offensive content in visible collections
* Do not feature new collections prominently (i.e. on the homescreen.)  Make new collections available but only on collections screen, through search, etc. Once the collection receives a good reputation (many views, many installs from views, likes, etc.) allow it to be featured on the home screen.
* Allow users to flag content for abuse
* Do not allow users to post urls in titles/descriptions (main source of spam for AMO)
* Auto-flag suspicious collections that appear to be spam and have them added to a review queue
* Filter for users creating many, many collections (100s of collections)
* Filter for users frequency of collection making (100s of collection in small amount of time)
* Filter for duplicate collections (often spam bot)
* Create a black list of banned users


## <a name="userstories">User Stories</a>
### Mobile
* As a user I want to add an app to an existing collection from the app details screen [github issue](https://github.com/mhanratty/marketplaceux-usercollections/issues/9) | [spec](#addappexistingcollection)
* As a user I want to add an app to a new collection from the app details screen  [githhub issue](https://github.com/mhanratty/marketplaceux-usercollections/issues/10) | [spec](#addappnewcollection)
* As a user I want to create a new collection from the "Collections" screen [githhub issue](https://github.com/mhanratty/marketplaceux-usercollections/issues/11) | [spec](#createcollection)
* As a user I want a place where I can view all of my collections [githhub issue](https://github.com/mhanratty/marketplaceux-usercollections/issues/19) | [spec](#collectionsscreen)
* As a user I want a dedicated place to view user collections on the Marketplace [github issue](https://github.com/mhanratty/marketplaceux-usercollections/issues/23) | [spec](#communityscreen)
* As a user I want an app wish list to store apps for later [githhub issue](https://github.com/mhanratty/marketplaceux-usercollections/issues/1) | [spec](#appwishlist)
* As a user I want to be able to remove an app from a collection [githhub issue](https://github.com/mhanratty/marketplaceux-usercollections/issues/13) | [spec](#removeapp)
* As a user I want to be able to delete a collection [githhub issue](https://github.com/mhanratty/marketplaceux-usercollections/issues/4) | [spec](#deletecollection)
* As a user I want to be able to customize the background of my collection graphic [githhub issue](https://github.com/mhanratty/marketplaceux-usercollections/issues/12)  | [spec](#changecollectionbackground)
* As a user with 0 collections I want to see a message about what the heck collections are! [githhub issue](https://github.com/mhanratty/marketplaceux-usercollections/issues/3) | [spec](#collectionsscreen)
* As a user I want to be able to see stats on my collections (number of shares, upvotes and views) | [spec](#collectionsscreen)
* As a user I want to be able to edit my avatar and display name that appears on the collection
* As a user I want a default avatar if I do not have a profile pic yet

### Desktop
* As a user I want to view my collections on desktop [github issue](https://github.com/mhanratty/marketplaceux-usercollections/issues/28)
* As a user I want to create a collection on desktop [github issue](https://github.com/mhanratty/marketplaceux-usercollections/issues/29)


## <a name="specs">Specs</a>
<a name="addappexistingcollection">![he can see so much more](http://mhanratty.github.io/marketplaceux-usercollections/img/usercollections_addappexistingcollection.png)</a>

<a name="addappnewcollection">![he can see so much more](http://mhanratty.github.io/marketplaceux-usercollections/img/usercollections_addappnewcollection.png)</a>

<a name="createcollection">![he can see so much more](http://mhanratty.github.io/marketplaceux-usercollections/img/usercollections_createcollection.png)</a>

<a name="collectionsscreen">![he can see so much more](http://mhanratty.github.io/marketplaceux-usercollections/img/usercollections_collectionsscreen.png)</a>

<a name="communityscreen">![he can see so much more](http://mhanratty.github.io/marketplaceux-usercollections/img/usercollections_communityscreen.png)</a>

<a name="appwishlist">![he can see so much more](http://mhanratty.github.io/marketplaceux-usercollections/img/usercollections_appwishlist.png)</a>

<a name="removeapp">![he can see so much more](http://mhanratty.github.io/marketplaceux-usercollections/img/usercollections_removeapp.png)</a>

<a name="deletecollection">![he can see so much more](http://mhanratty.github.io/marketplaceux-usercollections/img/usercollections_deletecollection.png)</a>

<a name="changecollectionbackground">![he can see so much more](http://mhanratty.github.io/marketplaceux-usercollections/img/usercollections_changecollectionbackground.png)</a>


