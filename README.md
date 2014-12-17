HPCIDemoIVRJava6 v1.0 Dec 16 2014
================

HostedPCI Demo IVR Implementation for Phone Session Service

What is it?
============
HPCIDemoIVR is a small app that will help customers implement the HostedPCI API when they want to use the 
HostedPCI Phone Session services.

What does this service do?
=========================
The HostedPCI Phone Session service designed to help companies who need to take credit card information from customers
over the phone. For example, insurance call centers who want to become PCI compliant.

How does it work?
=================
1. The HPCIDemoIVRJava6 app makes a call to the HostedPCI server and creates a session.
2. The CSR (Customer Support Representitive) makes a 3 way phone call and enters the session key number.
3. The IVR asks the customer to punch in his credit card and cvv numbers.
4. The IVR verifies the information.
5. If everything checks out, the IVR returns a token back to the HPCIDemoIVRJava6 app.
6. The CSR takes all other required information from the client (name, address, phone number) and fills in the form
   and submits.
7. The application takes in the token and all other required information and calls HostedPCI to process payment.
8. The application reads back the answer from HostedPCI and displays it to the CSR.

Release information
===================
Version 1.0, Dec 16 2014

Java JDK 6
Jquery 2.1.1
Bootstrap 3.2
Jetty 8.1.2
Browser

Installation
============
There are 2 methods of running it:
Using RunJettyRun plugin within Eclipse, or using JettyRunner.jar and HPCIDemoIVRJava6.jar from 
terminal/command prompt.
Using Eclipse:
==============
1. Set RunJettyRun to be assosiated with HPCIDemoIVRJava6 and set it to the desired port (I.E 8799).
2. Run using Jetty.
3. Open your browser and go to http://localhost:8799/index.jsp
4. Press on Create Session button, a session key will show up.
5. Call the HostedPCI IVR (you get the number from HostedPCI).
6. Enter the session key, enter the credit card and enter the cvv.
7. Press the Update Progress button which if everything went well, will automatically fill the token in the form.
8. Fill in the rest of the required information.
9. Press Process Payment button.
10. Results will be displayed at the bottom of the page.

Using Jetty Runner:
===================
1. Download HPCIDemoIVRJava6.war and Jetty-runner.jar.
2. Open the terminal/command prompt and go to the folder where both files are.
3. Type “java -jar jetty-runner.jar --stats unsecure --log yyyy_mm_dd-requests.log --port 8799 --out yyyy_mm_dd-output.txt HPCIDemoIVRJava6.war”
4. If everything went well, you should see something like this and a blinking cursor afterwards:
2014-10-08 10:33:36.843:INFO::main: Logging initialized @71ms
2014-10-08 10:33:36.848:INFO:oejr.Runner:main: Runner
2014-10-08 10:33:36.850:INFO:oejr.Runner:main: Redirecting stderr/stdout to yyyy_mm_dd-output.txt
5. Open any browser and type in http://localhost:8799/index.jsp
6. Create a new session, call the HostedPCI IVR number and enter the session key.
7. Follow the instructions by the IVR (you can enter a test credit card number 4111-1111-1111-1111).
8. If everything checks out, when you click on the Show Progress button, the form will now update with the credit card token that was given by the IVR.
9. Fill the rest of the form (MM/YY expiration has to be a future date).
10. Press the Process Payment button.
11. You will see the results of the payment process at the bottom of the page.

Contacts
=========
HostedPCI Inc.
http://www.hostedpci.com/
sales@hostedpci.com
1-866-850-3608

