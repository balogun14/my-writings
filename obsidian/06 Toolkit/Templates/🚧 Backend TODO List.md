---
Date-Created: 2024-07-07
tags:
  - "#🌱"
  - "#Distilled"
  - Note
  - "#⚗️"
Type: "[[Distilled]]"
Connected:
---
---
Date-Created: 
tags:
  - "#🌱"
  - "#Distilled Note"
  - "#⚗️"
Type: "[[Distilled]]"
Connected:
---
⬆️:: 

## Note⬆️:: 

[## ---
tags:
  - My/Learning
Category:
  - Learning
Date-Created: 
Source: []
Length: 
Priority: 
Topic-Area:
  - Learning
Learning Status:
  - Doing Now
Creator: 
Recommendation: ⭐
Video-URL: 
Summary:
---
⬆️:: 

## Learning Notes

[] Auth](<Here’s a clean and structured **Markdown TODO list** for the backend development based on the endpoints you shared:

---
## ✅ AUTH MODULE

- [ ] **SIGN UP**
  - Inputs: `name`, `email`, `phone number`, `gender`
  - Endpoint: `POST /auth/signup`

- [ ] **VERIFY OTP**
  - Inputs: `phone number`, `otp`
  - Endpoint: `POST /auth/verify`

- [ ] **SET PASSWORD**
  - Inputs: `password`, `confirm password`
  - Endpoint: `POST /auth/set-password`

- [ ] **PROFILE SETUP**
  - Inputs: `full name`, `number`, `email`, `street`, `city`, `district`
  - Endpoint: `POST /auth/profile`

- [ ] **SIGN IN**
  - Inputs: `email`, `password`
  - Endpoint: `POST /auth/signin`

- [ ] **LOG OUT**
  - Endpoint: `POST /auth/logout`

---

## 🛵 RIDING MODULE

- [ ] **FIND DRIVER**
  - Inputs: Depends on use-case (e.g. pickup/drop-off coordinates)
  - Endpoint: `POST /riding/find-driver`

- [ ] **ACCEPT DRIVER**
  - Inputs: `driver_id`, `ride_id` (?)
  - Endpoint: `POST /riding/accept-driver`

- [ ] **PAY**
  - Inputs: `payment_method`, `ride_id`, etc.
  - Endpoint: `POST /riding/pay`

---

## 📍 TRACKER MODULE

- [ ] **TRACK RIDE**
  - Inputs: `ride_id`
  - Endpoint: `GET /tracker/track-ride`

---

## ⚙️ SETTINGS

- [ ] **SETTINGS ENDPOINT**
  - Description/inputs TBD
  - Endpoint: `GET/POST /settings`

---

## 📞 CONTACT US

- [ ] **CONTACT SUPPORT**
  - Inputs: `name`, `email`, `message`
  - Endpoint: `POST /support/contact-us`

---

## ❌ DELETE ACCOUNT

- [ ] **DELETE ACCOUNT**
  - Inputs: Authenticated user
  - Endpoint: `DELETE /account/delete`

---

