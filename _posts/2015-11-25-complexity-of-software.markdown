---
published: true
title: Complexity of Software
layout: post
---
How many moving parts are in application software? 

Well… I counted the IF’s and EVALUATE’s in one of the nine campuses supported by the University of California Office of the President.  Shaving some off for comment lines, it comes out to an average of 47 logic decisions per program, for over 2,000 programs. 

That doesn’t really tell the tale, since some of those modules are simpler than others.  How many moving parts to get something specific done?  … I counted the IF’s and EVALUATES’s in the payroll program that does the actual check write and direct deposit file creation. 
  
942 logic branches.  I shaved some off  knowing that some of the strings show up in comment statements.  Without counting them, I just subtracted an arbitrary but reasonable number (based on observation and my experiences with the style of coding in effect), and used 920.  There are a couple of EVALUATE’s too.   (‘CASE’ statements, for the non-COBOL audience.)  I didn’t count them, in order to further insure that my estimate would be on the conservative side.  
 
This program is executed once per pay cycle each month.  A total of  around 24,840 paychecks (both checks and direct deposit) are processed in a month for this campus. 

Each paycheck navigates this program, which means there are 24,840 * 920 = 22,852,800 logic decisions processed directly in the check write program.  … But there are sub-programs executed -- about 35 of them.  If we assume that those sub-programs are of a more average level of complexity, and only have an average of 47 logic branches, and qualify it to say that only half of them are executed per paycheck, then we have 47 * 17 * 24,840 or an additional 19,847,160 decisions. 

 
The total number of logic decisions, for this one process, for one campus, for a single month is just under 42.7 million. 

One campus, out of nine supported campuses, representing about 18% of the total number of active employees paid.  For the entire month, for all pay cycles, for all campuses, you are looking at 237 million logic branches, just and only to create the pay deposits and checks.  

I don’t want to continue counting what the total number of decisions for a single month would be.  This **single process** represents quite a bit less than an hour of elapsed time per month out of a batch schedule that amounts to about 40 hours per month.  And, there is online processing executed as part of the application, running 12 hours per day every business day.  This being just 18% of the total workload for the payroll application running for the nine campuses.
 
I started thinking about this when a month or so ago I was at one of the kids activities that was held at a high school.  One of the dads there proudly mentioned that the construction company he works for built the school, a $180 million project.  Shortly after that, I came across the statistic that less than 10% of large IT projects (much smaller in total cost than that single high school construction) are fully successful. 

I didn’t wonder why that rate of less-than-complete success exists, nor the scary statistics regarding large software projects that go far beyond being over-budget and/or late in delivery into complete implosion, and are scrapped.  The reason, which most non-technologists don’t ponder: Software is among the most complex of human endeavors.

The high school might have 42 million parts, but they aren’t moving, and don’t have to navigate different paths on 24 thousand different unique combinations of decisions every month. …