### Working APIs

| No. | API Endpoint                                                                    | Description                                                                                   |
| --- | ------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- |
| 1   | `http://172.22.18.17:8096/api/AD/validateADDetails`                             | AD validation , for some reason only the email is validated the password is not authenticated |
| 2   | `http://172.22.18.17:8096/api/AD/GetADUsers`                                    | Fetch AD users                                                                                |
| 3   | `http://172.22.18.17:8000/authservices/api/ClientAccount/Login`                 | User login                                                                                    |
| 4   | `http://172.22.18.17:8000/coreservices/api/Services/GetAccountBalance`          | Get account balance                                                                           |
| 5   | `http://172.22.18.17:8000/coreservices/api/Services/IntraBankNameEnquiry`       | Name enquiry (intrabank)                                                                      |
| 6   | `http://172.22.18.17:8000/coreservices/api/Services/GetAllBanks`                | Get list of banks                                                                             |
| 7   | `http://172.22.18.17:8000/coreservices/api/Services/GetAccountDetail`           | Get account details                                                                           |
| 8   | `http://172.22.18.17:8000/coreservices/api/Services/GetCustomerAccounts`        | Get customer accounts                                                                         |
| 9   | `http://172.22.18.17:8000/coreservices/api/Services/GetBranches`                | Get bank branches                                                                             |
| 10  | `http://172.22.18.17:8000/postingservices/api/Posting/IntraBankAccountTransfer` | Post intrabank transfer                                                                       |
| 11  | `http://172.22.18.17:8000/coreservices/api/Services/GenerateOTP`                | Generate OTP                                                                                  |
| 12  | `http://172.22.18.17:8000/postingservices/api/Posting/IntraBankAccountRequery`  | Requery intrabank transfer                                                                    |

---

###  Issue - No Records Returned Despite Successful Transfer

| No. | API Endpoint                                                            | Issue Description                       |
| --- | ----------------------------------------------------------------------- | --------------------------------------- |
| 1   | `http://172.22.18.17:8000/coreservices/api/Services/FullStatement`      | Returned "No record could be retrieved" |
| 2   | `http://172.22.18.17:8000/coreservices/api/Services/TransactionHistory` | Same issue                              |
| 3   | `http://172.22.18.17:8000/coreservices/api/Services/MiniStatement`      | Same issue                              |

Affected Account: **All Account Numbers Provided**

---

### Not Working

| No. | API Endpoint                                                              | Issue                                                                                                          |
| --- | ------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------- |
| 1   | `http://172.22.18.17:8000/coreservices/api/Services/SendEmail`            | No validation for email format, throws internal server error sometimes , it fails also no success was observed |
| 2   | `http://172.22.18.17:8000/coreservices/api/Services/InterBankNameEnquiry` | Failed due to invalid test data                                                                                |
| 3   | `http://172.22.18.17:8000/coreservices/api/Services/SendSMS`              | Validation Error Occured                                                                                       |

**Sample Payload for Inter Bank Name Enquiry:**

```json
{
  "requestID": "-OwQoXl4jfyuI8QLqh7KnTvCOmFmTghMVxR3gNHN",
  "destAccount": "1010000145",
  "destBankCode": "421020",
  "channelCode": "string"
}
```

**Response:**

```json
{
  "destAccountName": null,
  "nameInquiryRef": null,
  "destAccountBVN": null,
  "kycLevel": null,
  "requestID": "-OwQoXl4jfyuI8QLqh7KnTvCOmFmTghMVxR3gNHN",
  "responseCode": "97",
  "responseMessage": "Unable to process"
}
```

---

**Sample Payload for Send SMS:**

```json
{
  "requestID": "19J9LZchWSGpCJlaftY51Z-Ee",
  "smsList": [
    {
      "receiver": "08156936535",
      "message": "Hi"
    }
  ]
}

```

**Response:**

```json
[{
  "destAccountName": null,
  "nameInquiryRef": null,
  "destAccountBVN": null,
  "kycLevel": null,
  "requestID": "Test1234690",
  "responseCode": "86",
  "responseMessage": "Invalid Account supplied."
}]({
  "type": "https://tools.ietf.org/html/rfc9110#section-15.5.1",
  "title": "One or more validation errors occurred.",
  "status": 400,
  "errors": {
    "Message": [
      "Message is required."
    ],
    "Receiver": [
      "Receiver is required."
    ]
  },
  "traceId": "00-792c0bac8aca9ef038ade4bfc8e8f7ad-e625393c9558122f-00"
})
```

-----

**Sample Payload for Send Email Enquiry:**

```json
[{
  "channelCode": "7",
  "destAccount": "8109925821",
  "destBankCode": "999050",
  "requestID": "Test1234690"
}]({
  "requestID": "FZ8sgLrtK9973LdQNXVqZhLF1YQrU5q",
  "to": "awwalbalogun06@gmail.com",
  "subject": "Hi",
  "body": "Testing Email Service",
  "cc": [
    "awwalbalogun87@gmail.com"
  ],
  "bcc": [
    ""
  ],
  "attachments": [
  ]
})
```

**Response:**

```json
{
  "requestID": "FZ8sgLrtK9973LdQNXVqZhLF1YQrU5q",
  "responseCode": "99",
  "responseMessage": "Send email failed"
}
```

###  Pending

|API|Status|
|---|---|
|Two Factor Authentication API (Token)|Still pending testing or details|

---

### NOT Tested

| No. | API Endpoint                                                     | Reason                                                                                                          |
| --- | ---------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------- |
| 1   | `http://172.22.18.17:8000/api/Services/InterBankTransfer`        | Blocked due to failed name enquiry and destination account also                                                 |
| 2   | `http://172.22.18.17:8000/coreservices/api/Services/ValidateOTP` | Need clarity on `platformUserId`, generateOTP seems to work but there is no way to check where OTP is sent also |
|     |                                                                  |                                                                                                                 |

---
