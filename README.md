# Unit-15-Homework-Web-Vulnerabilities-and-Hardening

### Part 1: Q&A

#### The URL Cruise Missile

The URL is the gateway to the web, providing the user with unrestricted access to all available online resources. In the wrong hands can be used as a weapon to launch attacks.

Use the graphic below to answer the following questions:

| Protocol         | Host Name                 | Path                   | Parameters               |
| ---------------- | :-----------------------: | ---------------------- | ------------------------ |
| **http://**      | **`www.buyitnow.tv`**     | **/add.asp**           | **?item=price#1999**     |


1. Which part of the URL can be manipulated by an attacker to exploit a vulnerable back-end database system? 
   * Parameters
   
2. Which part of the URL can be manipulated by an attacker to cause a vulnerable web server to dump the `/etc/passwd` file? Also, name the attack used to exploit this vulnerability.
   * Path
   
3. Name three threat agents that can pose a risk to your organization.
   * Nation States
   * Hacktivists
   * Developers

4. What kinds of sources can act as an attack vector for injection attacks?
   * SQL coding.

5. Injection attacks exploit which part of the CIA triad?
   * confidentiality and integrity of the CIA triad

6. Which two mitigation methods can be used to thwart injection attacks?
   * Disable web server directory listings, ensure backup files aren’t present in web roots.
   * Ensure logging of all access control failures and immediate generation of alerts.
____

#### Web Server Infrastructure

Web application infrastructure includes  sub-components and external applications that provide  efficiency, scalability, reliability, robustness, and most critically, security.

- The same advancements made in web applications that provide users these conveniences are the same components that criminal hackers use to exploit them. Prudent security administrators need to be aware of how to harden such systems.


Use the graphic below to answer the following questions:

| Stage 1        | Stage 2             | Stage 3                 | Stage 4              | Stage 5          |
| :------------: | :-----------------: | :---------------------: | :------------------: | :--------------: |
| **Client**     | **Firewall**        | **Web Server**          | **Web Application**  | **Database**     |
   
   
1. What stage is the most inner part of the web architecture where data such as, customer names, addresses, account numbers, and credit card info, is stored?
   * Stage 5

2. Which stage includes online forms, word processors, shopping carts, video and photo editing, spreadsheets, file scanning, file conversion, and email programs such as Gmail, Yahoo and AOL.
   * Stage 4

3. What stage is the component that stores files (e.g. HTML documents, images, CSS stylesheets, and JavaScript files) that's connected to the Internet and provides support for physical data interactions between other devices connected to the web?
   * Stage 3

4. What stage is where the end user interacts with the World Wide Web through the use of a web browser?
   * Stage 1

5. Which stage is designed to prevent unauthorized access to and from protected web server resources?
   * Stage 2

----


#### Server Side Attacks

In today’s globally connected cyber community, network and OS level attacks are well defended through the proper deployment of technical security controls such as, firewalls, IDS, Data Loss Prevention, EndPoint and security. However, web servers are accessible from anywhere on the web, making them vulnerable to attack.

1. What is the process called that cleans and scrubs user input in order to prevent it from exploiting security holes by proactively modifying user input.
   * Input sanitization

2. Name the process that tests user and application-supplied input. The process is designed to prevent malformed data from entering a data information system by verifying user input meets a specific set of criteria (i.e. a string that does not contain standalone single quotation marks).
   * Input validation

3. **Secure SDLC** is the process of ensuring security is built into web applications throughout the entire software development life cycle. Name three reasons why organization might fail at producing secure web applications.
   * High Implementation costs
   * Insufficient support from management
   * Insufficient standardization

4. How might an attacker exploit the `robots.txt` file on a web server?
   * Experienced criminal hackers will attempt to harvest the robots.txt file to retrieve private data, such as content management system information and root directory structure.

5. What steps can an organization take to obscure or obfuscate their contact information on domain registry web sites?
   * An organization can contact the domain provider and check the contact information using `whois`.
   
6. True or False: As a network defender, `Client-Side` validation is preferred over `Server-Side` validation because it's easier to defend against attacks.

   - Explain why you chose the answer that you did.
   - True, as a network defender, Client-side validation is easier because firewalls often fail to prevent client-side attacks, which occur behind the firewall and from within        the local network.

____

#### Web Application Firewalls

WAFs are designed to defend against different types of HTTP attacks and various query types such as SQLi and XSS.

WAFs are typically present on web sites that use strict transport security mechanisms such as online banking or e-commerce websites.

1. Which layer of the OSI model do WAFs operate at?
   * WAFs are specialized firewalls that can operate at Level 7 of the OSI Layer.

2. A WAF helps protect web applications by filtering and monitoring what?
   * A WAF protects your web apps by filtering, monitoring, and blocking any malicious HTTP/S traffic traveling to the web application.

3. True or False: A WAF based on the negative security model (Blacklisting) protects against known attacks, and a WAF based on the positive security model (Whitelisting) allows pre-approved traffic to pass.
   * True
____

#### Authentication and Access Controls

Security enhancements designed to require users to present two or more pieces of evidence or credentials when logging into an account is called multi-factor authentication.

- Legislation and regulations such as The Payment Card Industry (PCI) Data Security Standard requires the use of MFAs for all network access to a Card Data Environment (CDE).

- Security administrators should have a comprehensive understanding of the basic underlying principles of how MFA works.

1. Define all four factors of multifactor authentication and give examples of each:

   - Factor 1
     * Standard login inputs (passwords, PIN, cognitive questions)
   
   - Factor 2
     * Physical keys (smartcards, hard tokens)
   
   - Factor 3
     * Biometrics (Iris/retina scans, hand geometry)
   
   - Factor 4
     * Location (GPS detection, callback to a home phone number)
   
2. True or False: A password and pin is an example of 2-factor authentication.
   * True
   
3. True or False: A password and `google authenticator app` is an example of 2-factor authentication.
   * True
   
4. What is a constrained user interface? 
   * Constrained user interface restricts what users can see and do based on their privileges. 
   * Context-dependent controls regulate activity-based functions, such as your ability to perform tasks like editing a document
----
____

### Part 2: The Challenge 

In this activity, you will assume the role of a pen tester hired by a bank to test the security of the bank’s authentication scheme, sensitive financial data, and website interface.


#### Lab Environment   

We'll use the **Web Vulns** lab environment. To access it: 
  - Log in to the Azure Classroom Labs dashboard. 
  - Find the card with the title **Web Vulns** or **Web Vulnerability and Hardening**.
  - Click the monitor icon in the bottom-right. 
  - Select **Connect with RDP**.
  - Use Credentials (azadmin:p4ssw0rd*)

- The lab should already be started, so you should be able to connect immediately. 

- Refer to the [lab setup instructions](https://cyberxsecurity.gitlab.io/documentation/using-classroom-labs/post/2019-01-09-first-access/) for details on setting up the RDP connection.

Once the lab environment is running, open the HyperV manager and make sure that the OWASPBWA and Kali box is running.

- Then, login to the Kali VM and navigate to the IP address of the OWASPBWA machine.

- Click the option for 'WebGoat' and start the WebGoat app.

- Use the credentials: `guest`:`guest`

On the bottom of the left side of the screen, click on `Challenge` and then choose `The Challenge`.

**Note:** A common issue with this lab is the Challange activity failing to start successfully. Hit the `Restart the Lesson` button in the top right if you get an error starting the activity.

### The Challenge Instructions

#### Challenge #1

Your first mission is to break the authentication scheme. There are a number of ways to accomplish this task.

- **Hint #1**: Sometimes, form fields are shy!

- **Hint #2**: Find the hidden JavaScript.

- **Hint #3**: You can appened `source?source=true` to the URL to read the source code. 

After completing the first challenge, you will be provided with an option to continue to the next challenge.

#### Challenge #2

Next, steal all of the credit card numbers from the database. 

 **Hint #1**: Sometimes cookies wear different clothes to change their appearances.

- **Hint #2**: Break your way into the conversation and inject your own ideas.

After completing the second challenge, you will be provided with an option to continue to the next challenge.


#### Challenge #3

Your final act is to deface the website using command injection. Follow the walkthrough below to help you get started. 

- After completing the second challenge, you will be provided with an option to continue to the next challenge.

   ![cracked credit cards](Images/credit_cards-cracked.png)

- There should be two webpages at the bottom of the window. The one on top is the original, and the one on the bottom is the defaced webpage.

   ![original webpage](Images/original_defaced.png)

- Start Foxy Proxy (WebScarab) to send all GET/POST requests from Firefox to the WebScarab proxy intercept.

   ![Foxy Proxy](Images/foxy_proxy_scab.png)

- Click **TCP** and then the **View Network** button and send the request to WebScarab.

   ![View Network](Images/view_network_tcp.png)

- The WebScarab window will open. 

   - In the **URL Encoded** tab, find the **File** and **Value** form fields. 
   - This is where you will perform your command injection.
   
    ![File Field](Images/webscarab_file_value_field.png)

- Next, perform a test and see if this shell is vulnerable to command injection. 

   - Type the following command into the Value field: `tcp && whoami && pwd`.
   
       - **Note:** Windows users can type `tcp && dir`. `dir` will return the directory as proof of vulnerability.
   
   - Click **Accept Changes**.
   
     ![whoami](Images/whoami_pwd_image.png)
   
   - On the next window, click **Accept Changes** twice.
   
     ![accept](Images/webscarab_2nd_window.png)
 
- Scroll to the bottom of the **Current Network Status** window and observe the results for both of the `whoami` and `pwd` commands.

    ![whoami & pwd](Images/whoami_pwd.png)

   - The results show that we are the root user and our current working directory is `/var/lib/tomcat6`.

   - This verifies the vulnerability, so proceed to the next step.

- Next, we'll locate the `webgoat_challenge_guest.jsp` file. 

   - Type the following command: `tcp && cd / && find . -iname webgoat_challenge_guest.jsp`.
   
      - **Note**: Windows users will need to type: `tcp && dir /s 'webgoat_challenge_guest.jsp'`
   
   ![find command](Images/webscarab_find_command.png)
   
   - The absolute path is: `./owaspbwa/owaspbwa-svn/var/lib/tomcat6/webapps/WebGoat/webgoat_challenge_guest.jsp`.
   
   ![absolute path](Images/webscarab_abolute_path.png)
   
   - Remember, our present working directory is `/var/lib/tomcat6`. Therefore, the relative path is `webapps/WebGoat/webgoat_challenge_guest.jsp`.
   
**Now it's your turn**   

 Now that we know where the webpage is, let's inject some text and deface it.

   - Click **TCP**, then click the **View Network** button to send the request to WebScarab.
   
   - Modify the Value field with the following command injection:
   
      - `tcp && cd webapps/WebGoat && echo you_have_been_hacked > webgoat_challenge_guest.jsp`
      
        - **Note**: Window users, type the following: `tcp && echo 'test' >; C:\Users\user\Downloads\.extract\webapps\WebGoat\webgoat_challenge_guest.jsp`
      
   - Click **Accept Changes** in WebScarab.
      
        ![deface command](Images/challenge_3/webscarab_deface_injection_command.png)
      
   - In the next window, click **Accept Changes** two more times.
      
        ![accept](Images/challenge_3/webscarab_2nd_window.png)

- You should get a message that says "Congratulations - You have defaced the site!"

   ![Congrats](Images/challenge_3/Congrats.png)

- Scroll to the bottom to see the defaced webpage.

   ![Solved](Images/challenge_3/defaced_webpage.png)

___

---
