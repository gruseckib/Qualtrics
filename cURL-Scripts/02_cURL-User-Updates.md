During an organization restructure you might need to change thousands of users email domains, or maybe you've segmented your user base into sub-categories of users for permissions or tracking. If you ever need to change user permissions, types, divisions, etc. in bulk, feel free to slap this into CMD (Windows key + R, "CMD" Enter) after your changes:

```bash
curl -X PUT -H "X-API-TOKEN: APITOKENHERE-H "Content-Type: application/json" -d "{ VARIABLESHERE }" "https://datacenter.qualtrics.com/API/v3/users/USERIDHERE"
```

- Make sure to replace "APITOKENHERE" with your token
- The user ID of whom you want to remove in place of "USERIDHERE"
- The 'datacenter.qualtrics.com' with your brands link
- Change VARIABLESHERE to whatever field in particular you would like to update

Here's some usual fields for VARIABLESHERE:

```bash
User Types = \"userType\": \"UT_5bifLdf0fN3c9\"
Division = \"divisionId\": \"DV_cwoa7sdVBGbUxL\"
Email = \"email\": \"Jeff.Ryan@Karlsbad.com\"
```

Practical Example - User Type Change (single-user):

```bash
curl -X PUT -H "X-API-TOKEN: APITOKENHERE-H "Content-Type: application/json" -d "{ \"userType\": \"UT_5bifLdf0fN3c9\" }" "https://datacenter.qualtrics.com/API/v3/users/USERIDHERE"
```

Practical Example - Mass User Type Change(multi-user):

```bash
curl -X PUT -H "X-API-TOKEN: APITOKENHERE-H "Content-Type: application/json" -d "{ \"userType\": \"UT_5bifLdf0fN3c9\" }" "https://datacenter.qualtrics.com/API/v3/users/USERIDHERE1"

curl -X PUT -H "X-API-TOKEN: APITOKENHERE-H "Content-Type: application/json" -d "{ \"userType\": \"UT_5bifLdf0fN3c9\" }" "https://datacenter.qualtrics.com/API/v3/users/USERIDHERE2"

curl -X PUT -H "X-API-TOKEN: APITOKENHERE-H "Content-Type: application/json" -d "{ \"userType\": \"UT_5bifLdf0fN3c9\" }" "https://datacenter.qualtrics.com/API/v3/users/USERIDHERE3"
```

My recommendation is to fully repeat each string is based upon restrictions of CMD, which has a hard defined character limit.  Pasting the full code above will submit each request individually and automatically, effectively providing a work-around for this CMD based restriction.

**For more information on building a mass file, please view [0_Automated Script Building](https://github.com/gruseckib/Qualtrics/blob/master/cURL-Scripts/0_Automated%20Script%20Building.md)**