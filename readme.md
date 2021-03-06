Use Google Drive API to Authorize a Node.js program to upload data into a specific Google drive.
--
### Step1. Creating a Service Account using the Google Developers Console

The google account of the developer does not need to be the same as the google account of the targe Google Drive.

1. From the Google Developers Console, select your project or create a new one.
2. API & Services -> Credentials -> Create credentials -> Select "Service account key".
3. New Serice Account. Choose "Service account name" and choose Role as Project Owner.
4. Download a json file containing API private key.

## Step2. In the target google drive, setup sharing permssion.   

1. Look for the `client_email` field in the downloaded json file.
2. In the target google drive folder, share itself to the `client_email`.
3. Get the target folder id:
    1. the url of the target google drive contains this id, https://drive.google.com/drive/folders/"target_folderid"
    2. Or you can use `getFilelist` function of this Node.js to list all file and folder id.

## Step3. Setup client_email, API private key and target folder ID  

Do one of the below steps.
* Rename the downloaded json file to `gdrive.json`, then put it in this Node.js project folder. Add one more key, "target_folderid": "xxx".  
* Or export environment variables, drive_email, drive_folderid, drive_key. Their values can be found in the json file.      

## Step4. Install dependencies 

`npm install`.

## Step5. Launch program.  

`npm run start`. By default, this program will upload `Carta.dmg` to target google drive folder.
