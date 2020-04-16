One of the things I need to do often is to audit my current clients user-list and remove inactive users to save seat space.  Normally, if I am removing 1,00 or so users, this could take a full day of manually clicking about the screen and typing 'delete' over and over.

To quickly remove a user from your Qualtrics brand, fill-in and run this bad boy:

```bash
curl -X DELETE -H "X-API-TOKEN: APITOKENHERE" "https://datacenter.qualtrics.com/API/v3/users/USERIDHERE"
```

- Make sure to replace "APITOKENHERE" with your token
- The user ID of whom you want to remove in place of "USERIDHERE"
- The 'datacenter.qualtrics.com' with your brands link

To mass remove contacts, style your code such as below:

```bash
curl -X DELETE -H "X-API-TOKEN: APITOKENHERE" "https://datacenter.qualtrics.com/API/v3/users/USERIDHERE1"

curl -X DELETE -H "X-API-TOKEN: APITOKENHERE" "https://datacenter.qualtrics.com/API/v3/users/USERIDHERE2"

curl -X DELETE -H "X-API-TOKEN: APITOKENHERE" "https://datacenter.qualtrics.com/API/v3/users/USERIDHERE3"
```

My recommendation to fully repeat each string is based upon restrictions of CMD, which has a hard defined character limit.  Pasting the full code above will submit each request individually and automatically, effectively providing a work-around for this CMD based restriction.

**For more information on building a mass file, please view [0_Automated Script Building](https://github.com/gruseckib/Qualtrics/blob/master/cURL-Scripts/0_Automated%20Script%20Building.md)**