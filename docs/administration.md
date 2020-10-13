
Diabot has several features for admins to manage the server and configure other commands diabot offers.

## Commands:
> [Usernames](#usernames)  
> [Rewards](#rewards)  
> [Admin Channels](#admin-Channels)  
> [Announce](#announce)  
> [Nightscout Administration](#nightscout-administration)  
> [Roles](#roles)



## Usernames
Admin can enforce usernames within the server via a customizable regex pattern, to (for example) stop users from avoiding mentions, hoisting their username with special characters, etc.  
For example, `.*[a-zA-Z0-9]{2,}.*` matches 2 alphanumeric characters in a row.  
Websites like [regexr](https://regexr.com/) can help making and testing patterns.

### Commands
- [Show/View Pattern](#showview-Pattern)  
- [Show/View Hint](#showview-hint)
- [Enable Enforcement](#enable-enforcement)
- [Disable Enforcement](#disable-enforcement)


#### Show/View Pattern
To set a new pattern for username enforcement, use:  
`diabot admin usernames pattern [regex pattern]`

For example, the following command will ensure at least 2 consecutive alphanumeric characters in each username:  
`diabot admin usernames pattern .*[a-zA-Z0-9]{2,}.*`

In addition, you can call the command without arguments to see the current pattern:  
`diabot admin usernames pattern`

#### Show/View Hint
You can set a "hint", or a short description of what the pattern does to tell the users what the requirements are:  
`diabot admin usernames hint [hint]`

For example, from the example of the previous subcommand:  
`diabot admin usernames hint Please make sure your nickname contains at least 2 alphanumerical characters`

Again, you can view the current hint by calling the command without arguments:  
`diabot admin usernames hint`

#### Enable Enforcement
Enable username pattern enforcement:  
`diabot admin usernames enable`


#### Disable Enforcement
Disable username pattern enforcement:  
`diabot admin usernames disable`



## Rewards
Rewards are a system of giving users in the server a role if they have the required role, and were active while the reward was active.  
This is useful for events where you want all members who were active during the event to gain and eventually retain a role from that event.  
Users can opt-out of the reward (and back in) at will, and admins can force users to opt-out.

### Commands
- [Add reward](#add-reward)  
- [Delete reward](#delete-reward)  
- [List rewards](#list-rewards)  
- [Opt user in to rewards](#opt-user-in-to-rewards)  
- [Opt user out of rewards](#opt-user-out-of-rewards)  
- [List all opt-outs](#list-all-opt-outs)  


#### Add reward
To create a new reward, specify the required role ID and the rewarded role ID:  
`diabot admin rewards add <required role ID> <reward role ID>`

#### Delete reward
To delete an existing reward, specify both the required role ID and the rewarded role ID:  
`diabot admin rewards delete <requirement role ID> <reward role ID>`

#### List rewards
To list all currently configured rewards:  
`diabot admin rewards list`

#### Opt user in to rewards
Admins can force a user to opt-in to rewards by specifying the user ID:
`diabot admin rewards optin <user ID>`

#### Opt user out of rewards
Likewise, admins can force a user to opt-out of rewards:  
`diabot admin rewards optout <user ID>`

#### List all opt-outs
To list all users who are opted out of receiving rewards:  
`diabot admin rewards listoptouts`



## Admin Channels
Admin channels are a way of limiting certain commands which may expose sensitive information from being triggered in public channels.

### Commands
- [Add an admin channel](#add-an-admin-channel)  
- [Remove an admin channel](#Remove-an-admin-channel)  
- [List admin channels](#list-admin-channels)


#### Add an admin channel
To add an admin channel, specify the channel ID:  
`diabot admin channels add <channel ID>`

#### Remove an admin channel
Likewise, to remove an admin channel:  
`diabot admin channels delete <channel ID>`

#### List admin channels
To list all admin channels in the server:  
`diabot admin channels list`


## Announce
Admins can write messages as diabot in public channels.

### Commands
- `diabot admin announce <channel ID> <message>`: Announce a message in a channel


## Nightscout Administration
Admins can manage the `nightscout` command's appearance and entries using this command.  
The `simple` subcommand can force certain channels to only show single-line nightscout responses to mitigate clutter from many people calling nightscout at the same time.

### Commands
- `diabot nightscoutadmin set <user ID> <url>`: Set Nightscout URL for a user  
- `diabot nightscoutadmin delete <user ID>`: Delete a configured nightscout URL  
- `diabot nightscoutadmin simple`: Simple-mode channel management  
  - `diabot nightscoutadmin simple list`: List all channels where diabot will use simple nightscout replies  
  - `diabot nightscoutadmin simple add <channel ID>`: Add a simple response channel  
  - `diabot nightscoutadmin simple delete <channel ID>`: Delete a simple response channel  


## Roles
A simple command to get all roles in a server

### Commands
- `diabot roles`: Get all roles in the server  