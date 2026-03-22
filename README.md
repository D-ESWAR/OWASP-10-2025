# OWASP-10-2025 -ROOM(1)
SOLVING LAB

# WHAT IS IAAA?

Identity - the unique account (e.g., user ID/email) that represents a person or service.

Authentication - proving that identity (passwords, OTP, passkeys).

Authorisation - what that identity is allowed to do.

Accountability - recording and alerting on who did what, when, and from where.

What does IAAA stand for?

Identity,Authentication,Authorisation,Accountability
# A01 BROKEN ACCESS CONTROL
1.If you don't get access to more roles but can view the data of another users, what type of privilege escalation is this?
 Answer:Horizontal
2.What is the note you found when viewing the user's account who had more than $ 1 million?
 Answer:THM{Found.the.Millionare!}
# A07: Authentication Failures
1.What is the flag on the admin user's dashboard?

<img width="427" height="424" alt="image" src="https://github.com/user-attachments/assets/786fa602-596e-4eff-a01d-272a5388e48b" />

<img width="914" height="430" alt="image" src="https://github.com/user-attachments/assets/2d65de73-ce91-4188-9c75-d1fed0a9bb19" />

Flag: THM{Account.confusion.FTW!}
# A09: Logging & Alerting Failures

1.It looks like an attacker tried to perform a brute-force attack, what is the IP of the attacker?

Answer: 203.0.113.45

<img width="878" height="421" alt="image" src="https://github.com/user-attachments/assets/7d6cc133-0b67-4d62-8f7c-d173fbf53127" />

2.Looks like they were able to gain access to an account! What is the username associated with that account?

Answer: admin
# AS02: Security Misconfigurations
Challenge : http://10.49.154.138:5002


<img width="1578" height="418" alt="image" src="https://github.com/user-attachments/assets/d074e4cc-f8fc-437a-bf80-73e486d9799b" />


3.What action did the attacker try to do with the account? List the endpoint the accessed.

Answer: /supersecretadminstuff

# Application Design Flaws-ROOM (2)
## AS02: Security Misconfigurations
Challenge : http://10.49.154.138:5002
<img width="1578" height="418" alt="image" src="https://github.com/user-attachments/assets/fe3bfc8a-ec8b-4ab6-a9ab-33edc30e94c4" />
we can give /api/user/admin or any aplhabets (guesssing normal and common directries)
<img width="702" height="289" alt="image" src="https://github.com/user-attachments/assets/b6bc692e-2d47-4992-8610-9a4a9f1d1b63" />
Flag: THM{V3RB0S3_3RR0R_L34K}
# AS03: Software Supply Chain Failures
Challenge : http://10.49.154.138:5003

Python file they given to us
<img width="1763" height="774" alt="image" src="https://github.com/user-attachments/assets/4f6e4689-1e96-49f1-b350-c450cef93eb5" />

we found check whterher they have information /api/health and /api/process.
In /api/helath-no information

In header missing content-type:application/json
<img width="1496" height="547" alt="image" src="https://github.com/user-attachments/assets/5c225e5f-e341-4084-aaad-de2fb2ee0c09" />

we found any info in python code ,her data=debug
<img width="688" height="443" alt="image" src="https://github.com/user-attachments/assets/d182cbf0-8201-4ef6-8126-578921193bdd" />
8074" />

passing parameter data=debug
<img width="1514" height="615" alt="image" src="https://github.com/user-attachments/assets/71de2e9b-6575-465c-acae-643d4e228d00" />

Flag:THM{SUPPLY_CH41N_VULN3R4B1L1TY}
# AS04: Cryptographic Failures
Challenge Link: http://10.49.154.138:5004/
<img width="1691" height="526" alt="image" src="https://github.com/user-attachments/assets/63d21009-f4cd-47c0-872e-ab9a7073aa42" />

view page source we found /static/js/decrypt.js

<img width="1600" height="659" alt="image" src="https://github.com/user-attachments/assets/261a59c8-7ed4-4302-8db0-3cba28dfb59a" />

click we see

<img width="493" height="233" alt="image" src="https://github.com/user-attachments/assets/8c17f51b-04f6-415c-aa9d-29b482607224" />

getting the informaiton of key implement in cyberchef

<img width="1600" height="802" alt="image" src="https://github.com/user-attachments/assets/d8bf644e-8d11-490e-b447-7866bd894fb6" />
 Flag: THM{CRYPTO_FAILURE_H4RDCOD3D_K3Y}









