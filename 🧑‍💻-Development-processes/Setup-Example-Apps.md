## Step 1
Clone the repo (e.g. example-app-react)

## Step 2
Setup credentials

1. Copy the code below to your user `.npmrc`:

```
; begin auth token
//pkgs.dev.azure.com/AB-Design/59b17b42-1fc0-42fd-89d2-2655cf83b317/_packaging/apollo-design-system/npm/registry/:username=AB-Design
//pkgs.dev.azure.com/AB-Design/59b17b42-1fc0-42fd-89d2-2655cf83b317/_packaging/apollo-design-system/npm/registry/:_password=[BASE64_ENCODED_PERSONAL_ACCESS_TOKEN]
//pkgs.dev.azure.com/AB-Design/59b17b42-1fc0-42fd-89d2-2655cf83b317/_packaging/apollo-design-system/npm/registry/:email=npm requires email to be set but doesn't use the value
//pkgs.dev.azure.com/AB-Design/59b17b42-1fc0-42fd-89d2-2655cf83b317/_packaging/apollo-design-system/npm/:username=AB-Design
//pkgs.dev.azure.com/AB-Design/59b17b42-1fc0-42fd-89d2-2655cf83b317/_packaging/apollo-design-system/npm/:_password=[BASE64_ENCODED_PERSONAL_ACCESS_TOKEN]
//pkgs.dev.azure.com/AB-Design/59b17b42-1fc0-42fd-89d2-2655cf83b317/_packaging/apollo-design-system/npm/:email=npm requires email to be set but doesn't use the value
; end auth token
```

2. From your ADO user settings Generate a Personal Access Token with `Packaging read & write` scopes.
![image.png](/.attachments/image-a55daed2-551c-4f72-bc8c-872aebbbde05.png)

3. Base64 encode the Personal Access Token.

One safe and secure method of Base64 encoding a string is to:

1. From a command/shell prompt run:
```
node -e "require('readline').createInterface({ historySize: 0, input: process.stdin, output: process.stdout }).question('PAT> ', p => { b64=Buffer.from(p.trim()).toString('base64'); console.log(b64);process.exit(); })"
```

2. Paste your personal access token value and press Enter/Return
3. Copy the Base64 encoded value

* Replace both `[BASE64_ENCODED_PERSONAL_ACCESS_TOKEN]` values in your user `.npmrc` file with your personal access token from Step 3.

## Step 3
From the root of the cloned repo run `npm i` to install the dependencies and once finished run `npm start` to start the application.
