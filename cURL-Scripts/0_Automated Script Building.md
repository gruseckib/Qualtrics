One thing you've noticed is that you need a methodology or tool to create these scripts in bulk, which can be very time consuming to do individually during mass user adds, updates or removals.

This first one in particular is for the removal of a specified account:

```bash
curl -X DELETE -H "X-API-TOKEN: APITOKENHERE" "https://datacenter.qualtrics.com/API/v3/users/USERIDHERE"
```

Let's talk the brand specific fields:
- Make sure to replace "APITOKENHERE" with your api-token, this can be found through the 'Qualtrics IDs' portion of your account settings
- Update 'datacenter.qualtrics.com' with your brands URL, for example this could be 'cURL_company.na.qualtrics.com' or 'Hobobikes.eu.qualtrics.com'

Once your script is up-to-date with your api-token and datacenter we can get to the utilization of the scripts.  Let's revisit our script to remove an account with our information added.

```bash
curl -X DELETE -H "X-API-TOKEN: lakjdf863023nv_343" "https://hobobikes.eu.qualtrics.com/API/v3/users/USERIDHERE1"

curl -X DELETE -H "X-API-TOKEN: lakjdf863023nv_343" "https://hobobikes.eu.qualtrics.com/API/v3/users/USERIDHERE2"

curl -X DELETE -H "X-API-TOKEN: lakjdf863023nv_343" "https://hobobikes.eu.qualtrics.com/API/v3/users/USERIDHERE3"

.....
```

I've added a fake example api-token (lakjdf863023nv_343), and a non-existent datacenter URL (hobobikes.eu.qualtrics.com).  Now let's say we need to populate USERIDHERE, for say, 100 users to repeat the script in bulk. 

1. Create an Excel file with all of the UserID's in column A that you wish to remove.  In this example we will call the column *Rem_User*
2. Save this Excel file as a CSV.
3. Paste the following into Microsoft Word, making sure that you are including 2 to 4 Enter/Return spaces after the code.

```bash
curl -X DELETE -H "X-API-TOKEN: lakjdf863023nv_343" "https://hobobikes.eu.qualtrics.com/API/v3/users/USERIDHERE1"
```
4. In Word click, *Mailings>Start Mail Merge>Directory*
5. Now click, *Select Recipients>Use an Existing List*
6. Navigate to your saved CSV file that includes the UserID's you want to remove
7. Replace, *USERIDHERE1* by clicking on *Insert Merge Field>Rem_User*
8. Click *Finish & Merge>Edit Individual Documents>OK*

This will repeat your script for all 100 users that we need to remove.  Now you can copy the entire Word document file and paste it into the windows CMD prompt, it will automatically processes all of the signified removals.

**NOTE: Be very careful with any script you're pushing through in bulk, it's VERY easy to remove wrong accounts or create accounts with errors, and without a confirmation if you are not careful.**