# 🎴 Bug Bounty Checklist

{% hint style="success" %}
Build your own Bug Bounty Check List or scroll down and check mine mostly inspired by these resources only.
{% endhint %}

{% embed url="https://github.com/0xmaximus/Galaxy-Bugbounty-Checklist" %}

{% embed url="https://jeweled-lathe-d5e.notion.site/Bugs-detailed-25ae98f3d3b648bba4e1ab155e6760cb" %}

{% embed url="https://github.com/daffainfo/AllAboutBugBounty" %}

{% embed url="https://github.com/sehno/Bug-bounty/blob/master/bugbounty_checklist.md" %}

{% embed url="https://github.com/KathanP19/HowToHunt" %}

{% embed url="https://alike-lantern-72d.notion.site/Web-Application-Penetration-Testing-Checklist-4792d95add7d4ffd85dd50a5f50659c6" %}

{% embed url="https://pentestbook.six2dez.com/others/web-checklist" %}

{% embed url="https://pentestbook.six2dez.com/enumeration/web" %}

{% embed url="https://pentestbook.six2dez.com/enumeration/webservices" %}

***

## My Bug Bounty Check Check List

***

{% hint style="success" %}
Grab PDF format:&#x20;

[https://drive.google.com/file/d/150VFlq7yzC3NydvoWLHGOZ\_mjdUR3pXB/view?usp=sharing](https://drive.google.com/file/d/150VFlq7yzC3NydvoWLHGOZ_mjdUR3pXB/view?usp=sharing)
{% endhint %}

## Functionality

### **Oauth**

* 1st Scenario

```jsx
**Reference: https://hackerone.com/reports/1074047
1. Attacker signs up on website using the victim's email (which is not registered yet).
2. Attacker sets a password and waits.
3. Later, the victim tries to sign up using OAuth (Google, MSN, etc.).
4. website allows the victim to log in via OAuth but does not check if 
   the account was already created with a password.
5. Since OAuth skips email verification, the attacker can now log in 
   using the password they set earlier.**
```

* 2nd scenario

```jsx
**Reference: https://www.youtube.com/watch?v=GfIC_qiZb-E
           https://medium.com/@ProwlSec/the-oauth-oversight-when-configuration-errors-turn-into-account-hijacks-5ed1f9c83d16
1. Log in using the attacker's email via OAuth.
2. Change the attacker's email to the victim's email.
3. The victim attempts to register or reset their password.
4. The attacker can still access the victim's account using OAuth with the attacker's email.**        
```

* 4th Scenario Host-Header Injection in Oauthh
  * https://hackerone.com/reports/317476
* Exploiting callback\_urls= parameter
  * https://www.linkedin.com/pulse/account-takeover-via-google-oauth-misconfiguration-izyits-e76ef/?trackingId=8AI%2FWBa3TECMDxldWaTWSw%3D%3D

***

### **CAPTCHA**

* set value to true (https://cysky0x1.medium.com/registration-captcha-bypass-ecdb6cd382d1)
* set captcha value to 1 and also set new content-length
* Send old captcha value.
* Send old captcha value with old session ID.
* Request captcha absolute path like www.url.com/captcha/1.png
* Change from POST to GET
* Remove captcha parameter

***

### **OTP System**

* Keep adding zero or country code before actual phone number eg  \
  0XXXXXXXXXX,  \
  00XXXXXXXXXX,  \
  000XXXXXXXXXX,  \
  +91XXXXXXXXXX
* **let the intruder run till correct OTP even if there is 401 or 429 status code**  \
  **reference: https://mokhansec.medium.com/the-2-200-ato-most-bug-hunters-overlooked-by-closing-intruder-too-soon-505f21d56732**
* **if OTP in json format try make it array**
* **Response manipulation / false to true / correct OTP response.**
* **check developer tools**
* **Generate two OTP one from victim account second is attacker account**  \
  **Reference:** https://strangerwhite.medium.com/bypassing-otp-verification-another-bug-found-without-any-tools-8b2c1013c3e7

***

### **2FA Misconfiguration**

* **With null or 000000**
* **2FA Code Reusability**
* **2FA Bypass through Oauth**
* **Lack of Brute-Force Protection**
* **2FA Code Leakage in Response**
* **Missing 2FA Code Integrity Validation**
*   **Response Manipulation / Status Code Manipulation**

    ```jsx
    **Reference: https://likithteki.medium.com/how-i-got-150-on-hackerone-for-my-first-bug-8af0ed515e79
    1. Enable 2FA: Set up 2FA on the account and generate recovery codes.
    2. Save Codes: Securely store these recovery codes.
    3. Disable 2FA: Disable turn off 2FA.
    4. Re-enable 2FA: Reactivate 2FA on the account.
    5. Sign Out: Log out of the account.
    6. Login Attempt: Try logging back in using one of the old recovery codes.
    7. Despite re-enabling 2FA, the old recovery codes still worked, making it easy for an attacker to bypass the security measure.**
    ```
* **2FA bypass with password reset functionality.**  \
  https://www.linkedin.com/posts/alsanosi\_bugbounty-hackerone-bugcrowd-activity-7313613977844908033-VBFJ?utm\_source=share\&utm\_medium=member\_desktop\&rcm=ACoAAD7i-kYBPFLRnBLZy31myo6GBKvOJ3sZqKI

***

### **Swagger UI**

* https://scr1pty.medium.com/how-i-found-xss-in-swagger-ui-leading-to-account-takeover-on-bug-bounty-8d419c6b95d5
* https://infosecwriteups.com/hacking-swagger-ui-101-ccbce66ba028
* FOFA: domain="[http://redacted.com](https://t.co/sHWR76So3m)" && (icon\_hash="1120729672" || icon\_hash="-1128940573" || icon\_hash="-1180440057")

***

### **DMARC Policy**

{% embed url="https://mxtoolbox.com/" %}

{% embed url="https://www.anonymailer.net/m-mail-03.asp" %}

***

### **WordPress**

https://github.com/Raunaksplanet/CustomPayloads-Wordlist.com/blob/main/Fuzz-Wordpress.tx

https://github.com/Raunaksplanet/CustomPayloads-Wordlist.com/blob/main/wp-content.txt

***

### **My Profile Testing**

*   1st scenario

    ```jsx
    1. User A uploads a picture as "public".
    2. User B views the picture, right-clicks on the image, and opens it in a "new tab". User B now has the "direct URL" to the image.
    3. User A goes to their profile and changes the image's privacy to "private".
    4. Despite the privacy change, "User B can still access the image" using the "same direct URL".
    5. https://github.com/Tedixx/i/raw/i/i.zip
    ```
* Change account details (Name, Number, Address, etc.) Try CSRF
* EXIF Geolocation Data Not Stripped From Uploaded Images.

***

### **Signup Form testing**

* Rate limit on creating account
* Try to register with company mail
* **Parameter Pollution eg** https://www.linkedin.com/feed/update/urn:li:activity:7299260730627756032/
*   if email verification on registration then try HTMLI & Hyperlink injection

    ```jsx
    tracking link through htmli
    <img src="https://iplogger.co/142yV4" width="1" height="1" style="display:none;" />
    ```
* Check for insufficient email verification process and enable 2FA for account takeover
* Long password (>10k char) leads to DoS)
* Weak registration implementation-Allows disposable email addresses
* try id@ in registration page  \
  (reference: https://medium.com/@iski/how-i-found-my-first-high-severity-bug-and-got-rewarded-with-3-trays-of-red-bull-29ec0ca6a2e4)
* If JSON request, add comma {“email”:“victim@mail.com”,”hacker@mail.com”,“token”:”xxxxxxxxxx”}
* try to register with company email.

***

### **Signin Form testing**

* login rate limit bypass
* response manipulations
* directory bruteforce
* XSS on any other parameters found

***

### **File Upload**

1. **try adding magic bytes**   \
   **eg:** https://www.youtube.com/watch?v=oUI38IEqimM
2.  **Unrestricted File Upload via Double Extension Bypass**

    ```jsx
    The application validates uploads using only the file extension 
    (e.g., .jpg, .png). Uploading a file like shell.php.png bypasses 
    this check. The server treats it as a valid image but stores it with 
    its original name, enabling code execution if accessed directly.

    1. Create a PHP web shell (e.g., <?php system($_GET['cmd']); ?>) and save it as shell.php.png.
    2. Upload this file via the image upload feature.
    3. Visit the uploaded file’s URL.
    4. If executed as PHP, append ?cmd=whoami to test RCE.
    ```
3.  **Unauthenticated Image Upload to Public Cloud Storage**

    ```jsx
    Description:
    Upload API accepts file uploads without requiring authentication headers 
    (e.g., session tokens). The file is stored in a cloud bucket and returns a 
    public URL.

    Steps to Reproduce:
    1. Intercept the upload request using Burp Suite.
    2. Remove all authentication headers (like Cookie, Authorization).
    3. Forward the request with the image file.
    4. Observe if the server returns a valid public URL.
    5. Open that URL in an incognito window to verify public access.
    ```
4.  **Bypass of Product Image Upload Limit**

    ```jsx
    Description:
    The frontend restricts users to 7 images per product. However, this is 
    enforced only via JavaScript, not server-side.

    Steps to Reproduce:
    1. Begin uploading 7 images via the UI.
    2. Intercept the final image upload request in Burp.
    3. Clone and modify the intercepted request to upload additional images (8th, 9th, etc.).
    4. Send the requests.
    5. Confirm by viewing the product page showing more than 7 images.
    ```
5.  **No Rate Limiting or Upload Quotas**

    ```jsx
    Description:
    There’s no limit to how many files can be uploaded in a short time. 
    This allows abuse via automated tools.

    Steps to Reproduce:
    1. Set up Burp Suite Intruder or a script using curl/python to 
    	 send multiple upload requests.
    2. Launch a burst of 100+ file uploads in rapid succession.

    Observe:
    No captcha or delay.
    Server accepts all requests.
    All files are successfully stored.
    ```
6.  **File Replacement Attack**

    ```jsx
    Some platforms let users replace existing files. If predictable URLs 
    or file IDs are used, you might overwrite other users' files.

    1. Upload a file and observe its storage URL or ID.
    2. Try uploading a new file with same ID or URL path via Burp.
    3. If the existing file is replaced without ownership check, report it.
    ```

***

### **Session Issue**

1st Scenario

```jsx
0. https://hackerone.com/reports/1162443
1. Go to https://exchangemarketplace.com/ and click on Sign In
2. Continue with Google Account
3. Use "EditThisCookie" Extension to export the cookies
4. Once you logged in - click on "EditThisCookie" Extension and export the cookies
5. Now open another browser and import those cookies - you can able to login an account by using cookies
6. Logout from your first browser - it should logout from another browser as well.
7. Now, login again with your google account - This time use old cookies.
8. By using old cookies, you can able to login victim's account. (Whenever victim's session is active)
```

2nd scenario

```jsx
1. Go to `https://targetsite.com` and log in with valid credentials.
2. Open "EditThisCookie" extension and export the current session cookies.
3. Open another browser (or incognito window) and import the same cookies using "EditThisCookie".
4. Confirm you are logged into the same account in both sessions.
5. In the original browser, go to account settings and "change the password".
6. Observe: the second session (imported one) is "still active" and can perform authenticated actions.
7. This confirms that "session was not invalidated" after the password change.
8. Impact: An attacker with a stolen session cookie can maintain access even after a password reset.
```

3rd scenario

```jsx
1. Login to your account on "https://targetsite.com".  
2. Go to the "Profile" section and update any field (e.g., name or bio).  
3. Intercept the "update request" using Burp Suite.  
4. "Send the intercepted request to Repeater" (do not send it yet).  
5. Now, "logout" from the application.  
6. Go back to "Repeater" and "send the saved update request".  
7. Login again and check the profile data.  
8. If the "update was successful after logout", the session is still valid — "vulnerability confirmed".
```

https://www.linkedin.com/posts/rohith-s-0b9b2b267\_bugbounty-bugbountyreports-bugbountyjourney-activity-7318306351510683648-7Qug?utm\_source=share\&utm\_medium=member\_desktop\&rcm=ACoAAD7i-kYBPFLRnBLZy31myo6GBKvOJ3sZqKI

***

### **Test user account lockout mechanism on brute force attack**

* Bypass rate limiting by tampering user agent to Mobile User agent
* Bypass rate limiting by using null byte

***

### **Account Deletion testing**

* Check IDOR
* Lack of password confirmation when deleting your account

***

### **Product Purchase Testing**

* Buy Now
  * Tamper product ID to purchase other high valued product with low prize
  * Tamper product data in order to increase the number of product with the same prize
* Gift/Voucher
  * Tamper gift/voucher count in the request (if any) to increase/decrease the number of vouchers/gifts to be used
  * Tamper gift/voucher value to increase/decrease the value of the voucher in terms of money. (e.g. $100 is given as a voucher, tamper value to increase, decrease money)
  * Reuse gift/voucher by using old gift values in parameter tampering
  * Check the uniqueness of gift/voucher parameter and try guessing other gift/voucher code
  * Use parameter pollution technique to add the same voucher twice by adding same parameter name and value again with & in the BurpSuite request
* Add/Delete Product from Cart
  * Tamper user id to delete products from other user's cart
  * Tamper cart id to add/delete products from other user's cart
  * Identify cart id/user id for cart feature to view the added items from other user's account
* Place Order
  * Tamper payment options parameter to change the payment method. E.g. Consider some items cannot be ordered for cash on delivery but tampering request parameters from debit/credit/PayPal/net banking option to cash on delivery may allow you to    \
    place order for that particular item
  * Tamper the amount value for payment manipulation in each main and sub requests and responses
  * Check if CVV is going in cleartext or not
  * Check if the application itself processes your card details and then performs a transaction or it calls any third-party payment processing company to perform a transaction
* Track Order
  * Track other user's order by guessing order tracking number
  * Brute force tracking number prefix or suffix to track mass orders for other users
* Wish list page testing
  * Check if a user A can add/remote products in Wishlist of other user B’s account
  * Check if a user A can add products into user B’s cart from his/her (user A’s) Wishlist section.
* Post product purchase testing
  * Check if user A can cancel orders for user B’s purchase
  * Check if user A can view/check orders already placed by user B
  * Check if user A can modify the shipping address of placed order by user B
* Out of band testing
  * Can user order product which is out of stock?
* **Invite User as Different roles (Privilege escalation)**
  * **invite two user one as admin(user A) second as normal(user B) and then change user B email to user A**    \
    **Eg** https://siratsami71.medium.com/from-user-to-admin-a-privilege-escalation-via-business-logic-7ae901be7d81

***

### **Functionality where user get credit on account creation**

* https://cysky0x1.medium.com/how-i-found-a-critical-bug-affecting-the-organization-and-changed-money-in-the-credit-balance-b92569df5352

***

### **Password update & password forgot testing**

*   1st scenario

    ```jsx
    1. Register with the email "testbug@gmail.com" on the website.  
    2. Request a "password reset" for "testbug@gmail.com".  
    3. Do "not" open the reset link you receive in your email.  
    4. Log in to the account with the original password.  
    5. Go to the "profile settings" and change the email from "testbug@gmail.com" to "testpry@gmail.com".  
    6. Open the "previous reset link" (received for "testbug@gmail.com").  
    7. If the reset link is still "working", it means the application does not invalidate the reset link after the email change.
    ```
*   2nd scenario

    ```jsx
    0. Password Reset Token Leakage via Host Header Poisoning (add X-FORWADED-HOST: <burp collaborator link> to get token)
    1. Go to the "password reset page" on the website, for example: "https://targetsite.com/password-reset".
    2. Enter your email (e.g., "testuser@example.com") and request a "password reset".
    3. The application will send a password reset email with a reset token URL, typically like:
     "https://targetsite.com/reset-password?token=<token>"
    4. "Intercept the request" for the password reset in a proxy like Burp Suite (or use a browser's developer tools).
    5. "Modify the Host header" in the request to a different value, such as:
     "Host: evil.com"
    6. "Forward the modified request" to the server.
    7. Observe the response from the server.
    8. If the server "leaks the reset token" or responds with any sensitive data related to the password reset process in response to the "poisoned Host header", this is a "Password Reset Token Leakage vulnerability".
    ```
*   3rd scenario

    ```jsx
    0. https://hackerone.com/reports/772886  
    1. Register with the email 'testuser@example.com' on the website.  
    2. Go to the "password reset page" and request a reset for 'testuser@example.com'.  
    3. You will receive a password reset email with a link like:  
       'https://targetsite.com/reset-password?token=<reset_token>'.  
    4. Open the "reset link" and change the password.  
    5. Open a "new tab" in the browser and visit the same reset link:  
       'https://targetsite.com/reset-password?token=<reset_token>'.  
    6. If the link "still works" and you are able to successfully change the password again, this is a vulnerability — the reset token is not invalidated after use.
    ```
* check if backend check email case sensitivity
* IDOR in reset link
* Append second email parameter and value
* Account lockout even after entering right password
* CSRF on update password
* Check if forget password reset link/code uniqueness
* Password reset link not expiring using same link for multiple password reset
* Token leak in referrer header while clicking to another link on new password page
* https://github.com/0xmaximus/Galaxy-Bugbounty-Checklist/tree/main/Reset%20Password%20vulnerabilities

