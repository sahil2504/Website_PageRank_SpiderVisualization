Simple Python Search Spider, Page Ranker, and Visualizer

This is a set of programs that emulate some of the functions of a 
search engine.  They store their data in a SQLITE3 database named
'spider.sqlite'.  This file can be removed at any time to restart the
process.   

You should install the SQLite browser to view and modify 
the databases from:

http://sqlitebrowser.org/

This program crawls a web site and pulls a series of pages into the
database, recording the links between pages.

Mac: rm spider.sqlite
Mac: python3 spider.py

Win: del spider.sqlite
Win: spider.py

Enter web url or enter: http://www.dr-chuck.com/
['https://www.srmist.edu.in']
How many pages:100
1 https://www.srmist.edu.in/ 68
2 https://www.srmist.edu.in/admission-international/ 67
....
....
....
How many pages:

In this sample run, we told it to crawl a website and retrieve two 
pages.  If you restart the program again and tell it to crawl more
pages, it will not re-crawl any pages already in the database.  Upon 
restart it goes to a random non-crawled page and starts there.  So 
each successive run of spider.py is additive.

Mac: python3 spider.py 
Win: spider.py

Enter web url or enter: https://www.srmist.edu.in
['https://www.srmist.edu.in']
How many pages:100
101 https://www.srmist.edu.in/placement/contacts 66
102 https://www.srmist.edu.in/placement/recruiters 66
How many pages:

You can have multiple starting points in the same database - 
within the program these are called "webs".   The spider
chooses randomly amongst all non-visited links across all
the webs.

If you want to dump the contents of the spider.sqlite file, you can 
run spdump.py as follows:

Mac: python3 spdump.py 
Win: spdump.py

(68, 1.0, 4.217381521306251, 1, 'https://www.srmist.edu.in')
(67, 1.0, 3.133347907860874, 14, 'https://www.srmist.edu.in/admission-international')
(66, 1.0, 3.074524378449108, 102, 'https://www.srmist.edu.in/placement/contacts')
(66, 1.0, 3.1245243784491086, 101, 'https://www.srmist.edu.in/placement/recruiters')
(66, 1.0, 3.074524378449108, 84, 'https://www.srmist.edu.in/placement/about-cdc')
(66, 1.0, 3.074524378449108, 83, 'https://www.srmist.edu.in/placement/about')
(65, 1.0, 3.0411910451157755, 55, 'https://www.srmist.edu.in/content/gateway-parents')
(64, 1.0, 2.376205050718017, 50, 'https://www.srmist.edu.in/soc')
(63, 1.0, 2.3377435122564787, 42, 'https://www.srmist.edu.in/aboutus/srm-university-where-you-have-freedom-take-wings')
(62, 1.0, 2.1745243784491093, 59, 'https://www.srmist.edu.in/Organizational-Chart')
(62, 1.0, 2.197633622146588, 41, 'https://www.srmist.edu.in/campus/studentlife')
(62, 1.0, 2.1948863693993355, 39, 'https://www.srmist.edu.in/campus/arts-culture')
(62, 1.0, 2.1933479078608737, 30, 'https://www.srmist.edu.in/school-law/about-the-department')
(61, 1.0, 2.1345243784491092, 108, 'https://www.srmist.edu.in/content/faculty-abroad-program')
(61, 1.0, 2.1745243784491093, 107, 'https://www.srmist.edu.in/sap')
(61, 1.0, 2.136062839987571, 96, 'https://www.srmist.edu.in/campus-life/students-counseling-service')
(61, 1.0, 2.1388100927348237, 92, 'https://www.srmist.edu.in/faculty-directory')
(61, 1.0, 2.1345243784491092, 86, 'https://www.srmist.edu.in/srmpedia-application-2017')
(61, 1.0, 2.1345243784491092, 77, 'https://www.srmist.edu.in/aboutus/how-and-when-apply')
(61, 1.0, 2.1345243784491092, 72, 'https://www.srmist.edu.in/aboutus/welcome-srm-hostels')
(61, 1.0, 2.1345243784491092, 71, 'https://www.srmist.edu.in/sustainability-cell')
(61, 1.0, 2.137487341412072, 70, 'https://www.srmist.edu.in/aboutus/building-details')
(61, 1.0, 2.1345243784491092, 64, 'https://www.srmist.edu.in/aboutus/panel-foreign-faculty')
(61, 1.0, 2.1345243784491092, 63, 'https://www.srmist.edu.in/content/strategic-alliance')
(61, 1.0, 2.136062839987571, 57, 'https://www.srmist.edu.in/aboutus/history')
(61, 1.0, 2.136062839987571, 56, 'https://www.srmist.edu.in/aboutus/vision-and-mission')
(15, 1.0, 0.4077160493827161, 557, 'https://www.srmist.edu.in/event-gallery-view/5733')
(15, 1.0, 0.4077160493827161, 533, 'https://www.srmist.edu.in/event-gallery-view/5674')
(15, 1.0, 0.4077160493827161, 522, 'https://www.srmist.edu.in/event-gallery-view/6326')
(15, 1.0, 0.4077160493827161, 487, 'https://www.srmist.edu.in/event-gallery-view/6354')
(15, 1.0, 0.4077160493827161, 470, 'https://www.srmist.edu.in/event-gallery-view/5524')
(15, 1.0, 0.4077160493827161, 455, 'https://www.srmist.edu.in/event-gallery-view/6378')
(15, 1.0, 0.4077160493827161, 444, 'https://www.srmist.edu.in/event-gallery-view/6406')
(15, 1.0, 0.4077160493827161, 433, 'https://www.srmist.edu.in/event-gallery-view/6420')
(15, 1.0, 0.4077160493827161, 432, 'https://www.srmist.edu.in/event-gallery-view/6415')
(15, 1.0, 0.4077160493827161, 420, 'https://www.srmist.edu.in/event-gallery-view/6430')
(15, 1.0, 0.4077160493827161, 408, 'https://www.srmist.edu.in/event-gallery-view/6450')
(15, 1.0, 0.4077160493827161, 406, 'https://www.srmist.edu.in/event-gallery-view/6451')
(15, 1.0, 0.4077160493827161, 370, 'https://www.srmist.edu.in/event-gallery-view/6672')
(15, 1.0, 0.4077160493827161, 368, 'https://www.srmist.edu.in/event-gallery-view/6680')
(6, 1.0, 1.1993827160493826, 114, 'https://www.srmist.edu.in/cdc/cdc-team-members')
(5, 1.0, 0.8422398589065256, 339, 'https://www.srmist.edu.in/admission-international/Eligibility/Management')
(5, 1.0, 0.20180436847103514, 117, 'https://www.srmist.edu.in/aboutus/research-at-srm')
(5, 1.0, 0.19763261429928097, 104, 'https://www.srmist.edu.in/campus/caste_discrimination')
(5, 1.0, 1.1082062454611474, 36, 'https://www.srmist.edu.in/erc/index.html')
(4, 1.0, 0.6993827160493827, 636, 'https://www.srmist.edu.in/admission-international/Admission-Procedure/Support_Services')
(4, 1.0, 0.15784832451499117, 312, 'https://www.srmist.edu.in/faculty-directory/w')
(4, 1.0, 0.15784832451499117, 311, 'https://www.srmist.edu.in/faculty-directory/v')
(4, 1.0, 1.0493827160493827, 122, 'https://www.srmist.edu.in/erc/contact.html')
(4, 1.0, 1.0493827160493827, 121, 'https://www.srmist.edu.in/erc/related_links.html')
....
....
....
181 rows.

This shows the number of incoming links, the old page rank, the new page
rank, the id of the page, and the url of the page.  The spdump.py program
only shows pages that have at least one incoming link to them.

Once you have a few pages in the database, you can run Page Rank on the
pages using the sprank.py program.  You simply tell it how many Page
Rank iterations to run.

Mac: python3 sprank.py 
Win: sprank.py 

How many iterations:1
1 0.28623692248744775
[(1, 5.0583195116269), (2, 0.31760160574104446), (3, 0.765222735435455), (10, 0.3960885208177083), (14, 2.4825745971736595)]

You can dump the database again to see that page rank has been updated:

Mac: python3 spdump.py 
Win: spdump.py

You can run sprank.py as many times as you like and it will simply refine
the page rank the more times you run it.  You can even run sprank.py a few times
and then go spider a few more pages sith spider.py and then run sprank.py
to converge the page ranks.

If you want to restart the Page Rank calculations without re-spidering the 
web pages, you can use spreset.py

Mac: python3 spreset.py 
Win: spreset.py 

All pages set to a rank of 1.0

Mac: python3 sprank.py 
Win: sprank.py 

How many iterations:1
1 0.28623692248744775
[(1, 5.0583195116269), (2, 0.31760160574104446), (3, 0.765222735435455), (10, 0.3960885208177083), (14, 2.4825745971736595)]

For each iteration of the page rank algorithm it prints the average
change per page of the page rank.   The network initially is quite 
unbalanced and so the individual page ranks are changing wildly.
But in a few short iterations, the page rank converges.  You 
should run prank.py long enough that the page ranks converge.

If you want to visualize the current top pages in terms of page rank,
run spjson.py to write the pages out in JSON format to be viewed in a
web browser.

Mac: python3 spjson.py 
Win: spjson.py 

Creating JSON output on spider.js...
How many nodes? 30
Open force.html in a browser to view the visualization

You can view this data by opening the file force.html in your web browser.  
This shows an automatic layout of the nodes and links.  You can click and 
drag any node and you can also double click on a node to find the URL
that is represented by the node.

If you rerun the other utilities and then re-run spjson.py - you merely
have to press refresh in the browser to get the new data from spider.js.

