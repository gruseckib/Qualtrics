So you're wanting to start managing your Qualtrics brand in a more efficient, faster and more automated way?  Perfect!  Let's set you up for the utilization of cURL through Windows command prompt.  First let's look at the general look of a code.

This first one in particular is for the removal of a specified account:

```bash
curl -X DELETE -H "X-API-TOKEN: APITOKENHERE" "https://datacenter.qualtrics.com/API/v3/users/USERIDHERE"
```

This second script is for the creation of a user for your brand:

```bash
curl -X POST -H 'X-API-TOKEN: APITOKENHERE' -H 'Content-Type: application/json' -d '{ \"username\": \"exampleuser@example.com\", \"firstName\": \"ExampleFirstName\", \"lastName\": \"ExampleLastName\", \"userType\": \"UT_34BTbZFYBn\", \"email\": \"exampleuser@example.com\", \"password\": \"examplepassword\", \"divisionId\": \"Exampledivision\" }' 'https://datacenter.qualtrics.com/API/v3/users'
```

Let's better understand the code presented above before we talk customization:
- -X is notation for 'Request'
- -d is notation for data, typically in user, brand, and division update scripts
- -H is a header for the request, this is where your API token or credentials will be contained

Let's talk the brand specific fields:
- Make sure to replace "APITOKENHERE" with your api-token, this can be found through the 'Qualtrics IDs' portion of your account settings
- Update 'datacenter.qualtrics.com' with your brands URL, for example this could be 'cURL_company.na.qualtrics.com' or 'Hobobikes.eu.qualtrics.com'

Once your script is up-to-date with your api-token and datacenter we can get to the utilization of the scripts.  Let's revisit our first script.

```bash
curl -X DELETE -H "X-API-TOKEN: lakjdf863023nv_343" "https://hobobikes.eu.qualtrics.com/API/v3/users/UR_123456789"
```

I've added a non-valid example api-token (lakjdf863023nv_343), URL (hobobikes.eu.qualtrics.com) and user ID (UR_123456789).  With this script populated with your brand specific information, and the user you wish to remove, you can now use the command prompt (Windows Key + R, then type CMD) to remove the user UR_123456789 from your brand.