Re: SSO import...





Courtney Cross


​
Chris Banwarth
​
you will need to remove the "&", and exclude Accounting, Nurses, Nurse Sup, Prescribers, and Superusers with ODBC(Sebastian, Chiho, me).

Definitely needs to be tested

Courtney Cross

Pronouns: She/Her

Manager of Data Analytics & Behavioral Health Informatics

  

O: 774.670.4203

F: 508.753.5051

courtney.cross@spectrumhealthsystems.org

10 Mechanic Street| Worcester, MA 01608

spectrumhealthsystems.org

 



 

From: Chris Banwarth <Chris.Banwarth@spectrumhealthsystems.org>
Sent: Wednesday, May 1, 2024 4:19 PM
To: Courtney Cross <courtney.cross@spectrumhealthsystems.org>
Subject: SSO import...
 
I've attached the documents Netsmart sent for SSO imports.

The only reason I'm sending these is because they mention querying "SYSTEM.radplus_users", but I don't think I need to do anything with tables for Monday (since it's a smaller group, I can just manually create the import file).

Probably would make sense to automate it for the other roll-out weeks, if possible.

If you (or Sebastian/Chiho) have a minute tomorrow/Friday to walk me through the import process, that would be great. I know you are busy, so don't stress. Worst case, I can just enable everyone manually Sunday night.

csb 

/* Christopher Banwarth

  * Application Integration Architect

  *

  * chris.banwarth@spectrumhealthsystems.org 

  * O: 774-670-4778

  *

  * 10 Mechanic Street, Suite 302 | Worchester, MA 01608

  * spectrumhealthsystems.org

  */

From: Lindley, Josh <JLindley@ntst.com>
Sent: Tuesday, April 16, 2024 10:10 AM
To: Chris Banwarth <Chris.Banwarth@spectrumhealthsystems.org>; Taylor, Josh <jtaylor2@ntst.com>; Jonathan Miller <Jonathan.Miller@spectrumhealthsystems.org>
Cc: Courtney Cross <courtney.cross@spectrumhealthsystems.org>; DL_NPC_HHS_Delivery_NIAM_OPs <DL_NPC_HHS_Delivery_NIAM_OPs@ntst.com>; Lindley, Josh <JLindley@ntst.com>
Subject: RE: Please disable SSO on UAT...
 
Hey Chris,

 

Attached is the specs and a sample user file import.  A couple things to note.

 

You’ll delete row 1 before running the file. Those are just the column headers/descriptions
If a field doesn’t have any data from querying the SYSTEM.radplus_users table, leave that column blank in the user file import
Column E will have a value of 2  and Column H will have a value of Y for all users that are to be NIAM enabled.
Warnings are good when you go to run the import.
 

If you run into any issues running the import, please send me a copy of your User File Import. I can take a look at it.

 

Regards,

Josh

 

 

Netsmart icon

Josh Lindley Technical Project manager

D: 614.408.7260

At Netsmart, we believe EveryDayMatters®

 

Upcoming OOO: 

 

 

From: Chris Banwarth <Chris.Banwarth@spectrumhealthsystems.org>
Sent: Monday, April 15, 2024 10:27 AM
To: Lindley, Josh <JLindley@ntst.com>; Taylor, Josh <jtaylor2@ntst.com>; Jonathan Miller <jonathan.miller@spectrumhealthsystems.org>
Cc: Courtney Cross <courtney.cross@spectrumhealthsystems.org>; DL_NPC_HHS_Delivery_NIAM_OPs <DL_NPC_HHS_Delivery_NIAM_OPs@ntst.com>
Subject: Re: Please disable SSO on UAT...

 

CAUTION: This email originated from outside of the organization. Do not click links or open attachments unless you recognize the sender and know the content is safe. If you suspect this is a fraudulent email, please use Report Message -> Phishing in your Outlook banner to report this message.

 

 

Hi Josh -

 

Is there a template for the user definition upload?

 

Thanks.

 

csb

 

/* Christopher Banwarth

  * Application Integration Architect

  *

  * chris.banwarth@spectrumhealthsystems.org 

  * O: 774-670-4778

  *

  * 10 Mechanic Street, Suite 302 | Worchester, MA 01608

  * spectrumhealthsystems.org

  */

From: Lindley, Josh <JLindley@ntst.com>
Sent: Thursday, April 11, 2024 4:08 PM
To: Taylor, Josh <jtaylor2@ntst.com>; Jonathan Miller <Jonathan.Miller@spectrumhealthsystems.org>; Chris Banwarth <Chris.Banwarth@spectrumhealthsystems.org>
Cc: Courtney Cross <courtney.cross@spectrumhealthsystems.org>; DL_NPC_HHS_Delivery_NIAM_OPs <DL_NPC_HHS_Delivery_NIAM_OPs@ntst.com>; Lindley, Josh <JLindley@ntst.com>
Subject: RE: Please disable SSO on UAT...

 

The Widget for Telehealth has been updated as well. Our resource did want us to let you know that you’ll have to re-submit the user definition form for those users so they come across to the Telehealth tenant as Telehealth-enabled (similar to how to add new users to access Telehealth). Once you do that, they will be able to access the Telehealth via the widget.

 

Regards,

Josh

 

 

Netsmart icon

Josh Lindley Technical Project manager

D: 614.408.7260

At Netsmart, we believe EveryDayMatters®

 

Upcoming OOO: 

 

 

 

From: Taylor, Josh <jtaylor2@ntst.com>
Sent: Thursday, April 11, 2024 3:55 PM
To: Jonathan Miller <jonathan.miller@spectrumhealthsystems.org>; Lindley, Josh <JLindley@ntst.com>; Chris Banwarth <Chris.Banwarth@spectrumhealthsystems.org>
Cc: Courtney Cross <courtney.cross@spectrumhealthsystems.org>; DL_NPC_HHS_Delivery_NIAM_OPs <DL_NPC_HHS_Delivery_NIAM_OPs@ntst.com>
Subject: RE: Please disable SSO on UAT...

 

Jonathan,

 

              I have NIAM re-enabled in the UAT environment.

 

Respectfully,

 

 

Netsmart icon

Josh Taylor – SENIOR SYSTEM ENGINEER

Work Schedule: M-F / 08:00-17:00 CST

At Netsmart, we believe EveryDayMatters®

 

From: Jonathan Miller <Jonathan.Miller@spectrumhealthsystems.org>
Sent: Thursday, April 11, 2024 14:41
To: Lindley, Josh <JLindley@ntst.com>; Taylor, Josh <jtaylor2@ntst.com>; Chris Banwarth <Chris.Banwarth@spectrumhealthsystems.org>
Cc: Courtney Cross <courtney.cross@spectrumhealthsystems.org>; DL_NPC_HHS_Delivery_NIAM_OPs <DL_NPC_HHS_Delivery_NIAM_OPs@ntst.com>
Subject: RE: Please disable SSO on UAT...

 

CAUTION: This email originated from outside of the organization. Do not click links or open attachments unless you recognize the sender and know the content is safe. If you suspect this is a fraudulent email, please use Report Message -> Phishing in your Outlook banner to report this message.

 

 

Ok, let’s turn it back on in UAT and we can test again.  Thanks for taking a look at this.

 

 

Thanks,

 

Jonathan Miller

Chief Information Officer

Office: 774-670-4057

jonathan.miller@spectrumhealthsystems.org

10 Mechanic Street| Worcester, MA 01608

 

From: Lindley, Josh <JLindley@ntst.com>
Sent: Thursday, April 11, 2024 2:57 PM
To: Taylor, Josh <jtaylor2@ntst.com>; Jonathan Miller <Jonathan.Miller@spectrumhealthsystems.org>; Chris Banwarth <Chris.Banwarth@spectrumhealthsystems.org>
Cc: Courtney Cross <courtney.cross@spectrumhealthsystems.org>; DL_NPC_HHS_Delivery_NIAM_OPs <DL_NPC_HHS_Delivery_NIAM_OPs@ntst.com>; Lindley, Josh <JLindley@ntst.com>
Subject: RE: Please disable SSO on UAT...

 

Good Afternoon Jonathan,

 

We have identified the issue. There is a URL change needed for the Telehealth widget. We have that updated whenever you would like. The change will allow users that are NIAM enabled to access the widget, pending they have access to Telehealth. It won’t change anything for the non-NIAM enabled users.

 

Regards,

Josh

 

 

Netsmart icon

Josh Lindley Technical Project manager

D: 614.408.7260

At Netsmart, we believe EveryDayMatters®

 

Upcoming OOO: 

 

 

From: Taylor, Josh <jtaylor2@ntst.com>
Sent: Thursday, April 11, 2024 12:10 PM
To: Jonathan Miller <jonathan.miller@spectrumhealthsystems.org>; Chris Banwarth <Chris.Banwarth@spectrumhealthsystems.org>
Cc: Courtney Cross <courtney.cross@spectrumhealthsystems.org>; DL_NPC_HHS_Delivery_NIAM_OPs <DL_NPC_HHS_Delivery_NIAM_OPs@ntst.com>
Subject: Re: Please disable SSO on UAT...

 

Thank you, Jonathan.

 

      We'll work on getting an answer for you and getting this resolved. 

 

Respectfully,

 

 

Netsmart icon

Josh Taylor – SENIOR SYSTEM ENGINEER
Work Schedule: M-F / 08:00-17:00 CST

At Netsmart, we believe EveryDayMatters®

 

From: Jonathan Miller <Jonathan.Miller@spectrumhealthsystems.org>
Sent: Thursday, April 11, 2024 11:09 AM
To: Taylor, Josh <jtaylor2@ntst.com>; Chris Banwarth <Chris.Banwarth@spectrumhealthsystems.org>
Cc: Courtney Cross <courtney.cross@spectrumhealthsystems.org>; DL_NPC_HHS_Delivery_NIAM_OPs <DL_NPC_HHS_Delivery_NIAM_OPs@ntst.com>
Subject: RE: Please disable SSO on UAT...

 

CAUTION: This email originated from outside of the organization. Do not click links or open attachments unless you recognize the sender and know the content is safe. If you suspect this is a fraudulent email, please use Report Message -> Phishing in your Outlook banner to report this message.

 

 



 

Thanks,

 

Jonathan Miller

Chief Information Officer

Office: 774-670-4057

jonathan.miller@spectrumhealthsystems.org

10 Mechanic Street| Worcester, MA 01608

 

From: Taylor, Josh <jtaylor2@ntst.com>
Sent: Thursday, April 11, 2024 12:06 PM
To: Jonathan Miller <Jonathan.Miller@spectrumhealthsystems.org>; Chris Banwarth <Chris.Banwarth@spectrumhealthsystems.org>
Cc: Courtney Cross <courtney.cross@spectrumhealthsystems.org>; DL_NPC_HHS_Delivery_NIAM_OPs <DL_NPC_HHS_Delivery_NIAM_OPs@ntst.com>
Subject: Re: Please disable SSO on UAT...

 

Jonathan,

 

      I'd like to confirm that in the Supplemental Info tab is where that Organizational Email is populated, is that correct?

 

Respectfully,

 

 

Netsmart icon

Josh Taylor – SENIOR SYSTEM ENGINEER
Work Schedule: M-F / 08:00-17:00 CST

At Netsmart, we believe EveryDayMatters®

 

From: Jonathan Miller <Jonathan.Miller@spectrumhealthsystems.org>
Sent: Thursday, April 11, 2024 11:02 AM
To: Taylor, Josh <jtaylor2@ntst.com>; Chris Banwarth <Chris.Banwarth@spectrumhealthsystems.org>
Cc: Courtney Cross <courtney.cross@spectrumhealthsystems.org>; DL_NPC_HHS_Delivery_NIAM_OPs <DL_NPC_HHS_Delivery_NIAM_OPs@ntst.com>
Subject: RE: Please disable SSO on UAT...

 

CAUTION: This email originated from outside of the organization. Do not click links or open attachments unless you recognize the sender and know the content is safe. If you suspect this is a fraudulent email, please use Report Message -> Phishing in your Outlook banner to report this message.

 

 

We do have that organizational email completed.

 

Thanks,

 

Jonathan Miller

Chief Information Officer

Office: 774-670-4057

jonathan.miller@spectrumhealthsystems.org

10 Mechanic Street| Worcester, MA 01608

 

From: Taylor, Josh <jtaylor2@ntst.com>
Sent: Thursday, April 11, 2024 12:01 PM
To: Chris Banwarth <Chris.Banwarth@spectrumhealthsystems.org>
Cc: Jonathan Miller <Jonathan.Miller@spectrumhealthsystems.org>; Courtney Cross <courtney.cross@spectrumhealthsystems.org>; DL_NPC_HHS_Delivery_NIAM_OPs <DL_NPC_HHS_Delivery_NIAM_OPs@ntst.com>
Subject: RE: Please disable SSO on UAT...

 

Chris,

 

              I’ve got NIAM disabled in UAT. I believe that any Telehealth users will need to have their “Organizational Email” field filled out for that functionality to work.

 

 

Respectfully,

 

 

Netsmart icon

Josh Taylor – SENIOR SYSTEM ENGINEER

Work Schedule: M-F / 08:00-17:00 CST

At Netsmart, we believe EveryDayMatters®

 

From: Chris Banwarth <Chris.Banwarth@spectrumhealthsystems.org>
Sent: Thursday, April 11, 2024 10:54
To: Taylor, Josh <jtaylor2@ntst.com>
Cc: Jonathan Miller <jonathan.miller@spectrumhealthsystems.org>; Courtney Cross <courtney.cross@spectrumhealthsystems.org>
Subject: Please disable SSO on UAT...

 

CAUTION: This email originated from outside of the organization. Do not click links or open attachments unless you recognize the sender and know the content is safe. If you suspect this is a fraudulent email, please use Report Message -> Phishing in your Outlook banner to report this message.

 

 

Josh -

 

There is a showstopper for SSO: TeleHealth logins via Avatar no longer seem to work.

 

So we need to roll-back the functionality (we have a bunch of users going into UAT to test for NX).

 

csb

 

 

 

 

/* Christopher Banwarth

  * Application Integration Architect

  *

  * chris.banwarth@spectrumhealthsystems.org 

  * O: 774-670-4778

  *

  * 10 Mechanic Street, Suite 302 | Worchester, MA 01608

  * spectrumhealthsystems.org

  */

This email and its attachments may contain privileged and confidential information and/or protected health information (PHI) intended solely for the use of Netsmart Technologies and the recipient(s) named above. If you are not the recipient, or the employee or agent responsible for delivering this message to the intended recipient, you are hereby notified that any review, dissemination, distribution, printing or copying of this email message and/or any attachments is strictly prohibited. If you have received this transmission in error, please email compliance@NTST.com immediately and permanently delete this email and any attachments.

This email and its attachments may contain privileged and confidential information and/or protected health information (PHI) intended solely for the use of Netsmart Technologies and the recipient(s) named above. If you are not the recipient, or the employee or agent responsible for delivering this message to the intended recipient, you are hereby notified that any review, dissemination, distribution, printing or copying of this email message and/or any attachments is strictly prohibited. If you have received this transmission in error, please email compliance@NTST.com immediately and permanently delete this email and any attachments.

This email and its attachments may contain privileged and confidential information and/or protected health information (PHI) intended solely for the use of Netsmart Technologies and the recipient(s) named above. If you are not the recipient, or the employee or agent responsible for delivering this message to the intended recipient, you are hereby notified that any review, dissemination, distribution, printing or copying of this email message and/or any attachments is strictly prohibited. If you have received this transmission in error, please email compliance@NTST.com immediately and permanently delete this email and any attachments.

This email and its attachments may contain privileged and confidential information and/or protected health information (PHI) intended solely for the use of Netsmart Technologies and the recipient(s) named above. If you are not the recipient, or the employee or agent responsible for delivering this message to the intended recipient, you are hereby notified that any review, dissemination, distribution, printing or copying of this email message and/or any attachments is strictly prohibited. If you have received this transmission in error, please email compliance@NTST.com immediately and permanently delete this email and any attachments.

This email and its attachments may contain privileged and confidential information and/or protected health information (PHI) intended solely for the use of Netsmart Technologies and the recipient(s) named above. If you are not the recipient, or the employee or agent responsible for delivering this message to the intended recipient, you are hereby notified that any review, dissemination, distribution, printing or copying of this email message and/or any attachments is strictly prohibited. If you have received this transmission in error, please email compliance@NTST.com immediately and permanently delete this email and any attachments.