# Week-9-Lab
Twitter!

# Microblogging Social Network (Twitter)

## Description
Microblogging Social Network (Twitter)


## Objectives

### Learning Objectives

After completing this assignment, you should…

* Understand nuget and their place in c# development
* Understand Relationships between models
* Understand Personalization
* Understand Authentication


### Performance Objectives

After completing this assignment, you be able to effectively use

* authentication, sessions, and User.Identity
* Bootstrap
* Sql Server Database
* Deploying to Azure
* Validations
* Controllers



## Details

### Deliverables

* A repo containing at least:
  * a User model 
  * a Post model that Users can write
  * a Follow model

### Requirements

## Normal Mode

* Users can signup, and sign in
* User can follow other users
* User can see posts from [User + Friends] in their Timeline
* User can Post posts
* User can unfollow a person
* Site should look nice
* Posts should be paginated
* Data should be seeded using fake data

            
## Hard Mode
            
* User can view a profile (/users/dpollock)
* Users can block users for being a-holes
* Users can search for posts


## Notes

* When logged in, the root URL should show the messages from all the people you follow.
* Getting the list of messages for You + people you follow is tricky'ish. Think of it like this:

```c#
  List<Post> GetTimeLine()
  {  
	var followerIds = db.Following.Where(f=>f.FollowedById == MyUserId).Select(f=>f.Userid);
    var allIds = followerIds.Add(MyUserId);
    return db.Posts.Where(x=> allIds.Contains(x.PostedById)).OrderByDesc(x=>x.CreatedBy);
 }
```

## Additional Resources

* [ASP.NET Identity](http://www.asp.net/identity/overview/getting-started/introduction-to-aspnet-identity)
* [Free Bootstrap Themes](https://bootswatch.com/)
