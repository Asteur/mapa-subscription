# mapa-subscription
Helps to implement subscriptions for Mapa


# preparation 

- install node [https://nodejs.org/en/download/]
- install npm [https://www.npmjs.com/get-npm]
- install ts-node [https://www.npmjs.com/package/ts-node]
npm i typescript -S
- download archive
- unzip and go to /mapa-subscription folder
- then

        npm install

P.S.
- update initTransportSMTP with smtp server settings or gmail credentials (src/core/utils/email.util.ts)
To use your gmail account, turn on less secure apps in your account (https://myaccount.google.com/u/1/lesssecureapps)
- install curl/postman (to make requests) -> just google

# run API

        npm start (starts development server)

or

        npm start-prod (starts prod server)

API Requests:
-
Examples:

        curl -d '{"email":"aa@sd.com", "type":"I", "last_date": "1565122640", "subs_params":{"id":"123"}}' -H "Content-Type: application/json" -X POST http://localhost:3001/api/subscription

        curl -d '{"hashId":"fe24b489f8862f8ba21f17539271c2f16a7062cd"}' -H "Content-Type: application/json" -X DELETE http://localhost:3001/api/subscription

# run mailer

Before starting the mailer, be sure to add a few lines of data to the database, either manually or through the queries above.

        npx ts-node src/mailer.ts

or
(convert to js and run)

        npm i -g typescript
        ts-node src/mailer.ts


# TODO

- update and configure email template - raw data is send (src/core/utils/mailer.util.ts)
- update initTransportSMTP with smtp server settings - gmail is used (src/core/utils/email.util.ts)
s