
Solutions for BlackHat MEA challenges

## Warm me up

Visiting home page displays a link to login page.

![HomePage](https://github.com/Xib3rR4dAr/CTF_BlackHat_MEA_2023/assets/24238512/3f6f9e91-47d7-4019-80b0-a2889c6edffc)

Also, upon visiting homepage, a Cookie named `session` is returned in headers. Base64 decoding first part before dot (.) shows an OTP. This OTP was later tried in OTP field.

![image](https://github.com/Xib3rR4dAr/CTF_BlackHat_MEA_2023/assets/24238512/cff5b17e-4152-4992-a7e2-b1887afb2b0b)

Visiting Login page displays a form to enter Username, Password and OTP.

![image](https://github.com/Xib3rR4dAr/CTF_BlackHat_MEA_2023/assets/24238512/b669d591-5b15-42e4-a46f-ff08f1ea5ece)

Using single quote in `username` parameters gives error while using double quotes gives no error.

![image](https://github.com/Xib3rR4dAr/CTF_BlackHat_MEA_2023/assets/24238512/00378346-1080-46aa-8cf1-133ce66fa7bd)

![image](https://github.com/Xib3rR4dAr/CTF_BlackHat_MEA_2023/assets/24238512/7f530937-b173-4c7b-b914-aa056fc8fac9)

Using `' or 1=1-- -` or `admin'-- -` doesnot login.  

Using `' order by 2-- -` gives no error while `' order by 3-- -` gives error indicating that backend SQL query i using 2 rows.  

Using username as `' UNION SELECT 'admin','admin'-- -` with any password with OTP got from session cookie successfully logs us in and provides new session cookie.

![image](https://github.com/Xib3rR4dAr/CTF_BlackHat_MEA_2023/assets/24238512/00b84ea0-9e80-40b5-b8fc-092fdef58562)

Using received session cookie shows up the flag.

![image](https://github.com/Xib3rR4dAr/CTF_BlackHat_MEA_2023/assets/24238512/0ed5a1e3-15bf-4b30-8443-3a67b38b96fa)



