Here’s a table grouping the endpoints from `AdsController` and `BankRoleController` by similarity, prioritizing the `BankRoleController` structure:

| **Action Type**               | **BankRoleController Endpoint**                          | **AdsController Endpoint**                   |
| ----------------------------- | -------------------------------------------------------- | -------------------------------------------- |
| **Create**                    | `POST api/bank/v1/BankRole/CreateBankRole`               | `POST api/Ads/CreateAds`                     |
| **Get All**                   | `GET api/bank/v1/BankRole/GetBankRoles`                  | `GET api/Ads/GetAllAds`                      |
| **Get Paginated All**         | `GET api/bank/v1/BankRole/GetPaginatedBankRoles`         | -                                            |
| **Get Single**                | `GET api/bank/v1/BankRole/GetBankRole`                   | `GET api/Ads/GetAd`                          |
| **Get Pending**               | `GET api/bank/v1/BankRole/GetPendingBankRoles`           | `GET api/Ads/GetPendingAds`                  |
| **Get Paginated Pending**     | `GET api/bank/v1/BankRole/GetPaginatedPendingBankRoles`  | -                                            |
| **Get Single Pending**        | `GET api/bank/v1/BankRole/GetPendingBankRole`            | `GET api/Ads/GetPendingAd`                   |
| **Get Declined**              | `GET api/bank/v1/BankRole/GetDeclinedBankRoles`          | -                                            |
| **Get Paginated Declined**    | `GET api/bank/v1/BankRole/GetPaginatedDeclinedBankRoles` | -                                            |
| **Edit/Update**               | `POST api/bank/v1/BankRole/EditBankRole`                 | `POST api/Ads/EditAds`                       |
| **Deactivate**                | `POST api/bank/v1/BankRole/Deactivate`                   | `POST api/Ads/DeactivateAds`                 |
| **Approve**                   | `POST api/bank/v1/BankRole/Approve`                      | `POST api/Ads/ApproveRequest`                |
| **Decline**                   | `POST api/bank/v1/BankRole/Decline`                      | `POST api/Ads/DeclineRequest`                |
| **Request Reactivation**      | `POST api/bank/v1/BankRole/RequestReactivation`          | `POST api/Ads/RequestAdsReActivation`        |
| **Approve Reactivation**      | `POST api/bank/v1/BankRole/ApproveReactivation`          | `POST api/Ads/ApproveAdsReActivationRequest` |
| **Decline Reactivation**      | `POST api/bank/v1/BankRole/DeclineReactivation`          | `POST api/Ads/DeclineAdsReActivationRequest` |
| **Get Mode**                  | -                                                        | `GET api/Ads/GetAdsMode`                     |


### Notes
- **BankRole Preference**: Grouped based on `BankRoleController` actions (e.g., Create, Get, Approve).
- **Similarities**: Matched `AdsController` endpoints to closest `BankRole` equivalents by function.
- **Unique Endpoints**: Ads-specific actions (e.g., `GetAdsMode`) listed at the end.