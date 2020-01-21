One of the things I need to do often is to audit my current clients user-list and remove inactive users to save seat space.  Normally, if I am removing 1,00 or so users, this could take a full day of manually clicking about the screen and typing 'delete' over and over.

To quickly remove a user from your Qualtrics brand, fill-in and run this bad boy:

```bash
curl -X DELETE -H "X-API-TOKEN: APITOKENHERE" "https://datacenter.qualtrics.com/API/v3/users/USERIDHERE"
```

- Make sure to replace "APITOKENHERE" with your token
- the user ID of whom you want to remove in place of "USERIDHERE"
- The 'datacenter.qualtrics.com' with your brands link

To mass remove contacts, style your code such as below:

```bash
curl -X DELETE -H "X-API-TOKEN: APITOKENHERE" "https://datacenter.qualtrics.com/API/v3/users/USERIDHERE1" "https://datacenter.qualtrics.com/API/v3/users/USERIDHERE2" "https://datacenter.qualtrics.com/API/v3/users/USERIDHERE3"
```

My suggestion for building this massive one-lined script is to use =Concat with the double quotes, link, userID and double quotes again.  You can then copy all the links and paste it into Notepad++.  Ctrl + J will merge all of the information into a single line.