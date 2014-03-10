---
tags: test
---

# User Collections Design Spec

[Overview](#overview)

[Success Metrics](#successmetrics)

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

**User Collections Mobile Prototype 1** (Study conducted on UserTesting.com on December 18, 2013)
* *Purpose of Study*: Evaluate the experience and user understanding of creating a group of apps and sharing the group with the Marketplace community. The test will identify pain points with the user flow and usefulness of user collections. We also want to get feedback on potential names for the feature (collections, lists, etc.)
* *Prototype tested*: [http://people.mozilla.org/~mhanratty/user_collections_prototype_v1/home.html]
* *Key takeways*:
    * Flow of creating groups, adding an app to a group and sharing the group made sense to participants
    * People had difficulty disambiguating between "Share" and "Share with the Community." 
    * Participants did not come up with a consistent name for the feature
    * Participants talked about this feature in regards to organizing apps on their device 
* Test results report: (https://docs.google.com/a/mozilla.com/document/d/10eGrgyuM2wRjPcfe49nA_OsQx9e1tPQwPcL028D1lzc/edit)

**User Collections Desktop Prototype 1** (Study conducted on UserTesting.com on Febuary 06, 2014)
* *Purpose of Study*: Evaluate the experience and user understanding of creating a group of apps and sharing the group with the Marketplace community on the desktop. The test will identify pain points with the user flow and discoverability of user collections. We also want to get feedback on potential names for the feature (collections, lists, etc.).
* *Prototype tested*: http://people.mozilla.org/~mhanratty/User_Collections_Desktop_Prototype_02042014/home.html
* *Key takeways*:
    * Flow of creating groups, adding an app to a group and sharing the group made sense to participants.
    * People had difficulty finding the feature.
    * Participants preferred the name “collections” for the feature
    * Participants had difficulty finding the bottom toolbar to make the list public.
* Test results report: https://docs.google.com/document/d/15mKGX52-weGQXV7USfBzickyko83x0QZvSGjxQC4vAU/edit?usp=sharing

## <a name="successmetrics">Success Metrics</a>
* 20%


## <a name="userstories">User Stories</a>
* As a user I want to add an app to an existing collection from the app details screen [github issue](https://github.com/mhanratty/marketplaceux-usercollections/issues/9) | [spec](#addappexistingcollection)
* As a user I want to add an app to a new collection from the app details screen  [githhub issue](https://github.com/mhanratty/marketplaceux-usercollections/issues/10) | [spec](#addappnewcollection)
* As a user I want to create a new collection from the "Collections" screen [githhub issue](https://github.com/mhanratty/marketplaceux-usercollections/issues/11) | [spec](#createcollectionfromcollections)
* As a user I want a place where I can view all of my collections [githhub issue](https://github.com/mhanratty/marketplaceux-usercollections/issues/19)
* As a user I want a dedicated place to view user collections on the Marketplace [github issue](https://github.com/mhanratty/marketplaceux-usercollections/issues/23) | [spec](#communityscreen)
* As a user I want an app wish list to store apps for later [githhub issue](https://github.com/mhanratty/marketplaceux-usercollections/issues/1)
* As a user I want to be able to remove an app from a collection [githhub issue](https://github.com/mhanratty/marketplaceux-usercollections/issues/13)
* As a user I want to be able to delete a collection [githhub issue](https://github.com/mhanratty/marketplaceux-usercollections/issues/4)
* As a user I want to be able to customize the background of my collection graphic [githhub issue](https://github.com/mhanratty/marketplaceux-usercollections/issues/12)
* As a user with 0 collections I want to see a message about what the heck collections are! [githhub issue](https://github.com/mhanratty/marketplaceux-usercollections/issues/3)
* As a user I want to be able to see stats on my collections (number of shares, upvotes and views)
* As a user I want to be able to edit my avatar and display name that appears on the collection
* As a user I want a default avatar if I do not have a profile pic yet

## <a name="specs">Specs</a>
<a name="addappexistingcollection">![he can see so much more](http://mhanratty.github.io/marketplaceux-usercollections/img/usercollections_addappexistingcollection.png)</a>

<a name="addappnewcollection">![he can see so much more](http://mhanratty.github.io/marketplaceux-usercollections/img/usercollections_addappnewcollection.png)</a>

<a name="createcollectionfromcollections">![he can see so much more](http://mhanratty.github.io/marketplaceux-usercollections/img/usercollections_createcollectionfromcollections.png)</a>


<a name="communityscreen">![he can see so much more](http://mhanratty.github.io/marketplaceux-usercollections/img/usercollections_communityscreen.png)</a>


This is an [in-line link](http://www.mozilla.org).
This is an [in-line link](http://www.mozilla.org "Link with title") with a title.

Here's some reference style links to [sites][1] that are really cool [sites][2] about the [sites][3] on the Internetweb.

[1]: http://www.mozilla.com 
[2]: http://www.twitter.com
[3]: http://www.lolcatz.com

and here's Geordi

![he can see so much more](http://tsmuse.github.io/testMarketplaceDesignSpec/img/geordi.jpg)
