# Implementation_of_Persuasive_Cued_Click_Points
Research paper on the design, analysis and implementation of Persuasive Cued Click Points 

INTRODUCTION TO CLICK BASED GRAPHICAL PASSWORDS
Graphical password systems are a type of know based authentication that attempts to leverage the human memory for visual information. Cued-recall click-based graphical passwords (also known as locimetric) are a type of authentication in which users identify and target previously selected locations within one or more images. The images act as memory cues to aid recall. Best example would be PassPoints and Cued ClickPoints (CCP) [5], [9], [10], [11]. 

Another mechanism that comes into play is Persuasive Cued ClickPoints (PCCP), PCCP uses persuasion to influence user choice in click based graphical passwords, encouraging a user to select more random and hence more difficult to guess clickpoints. Persuasive technology was first articulated by Fogg as using technology to motivate and influence people to behave in a desirable manner. PCCP’s design follows Fogg’s principle of reduction by making the desired task of choosing a strong password easiest. Rather than increasing the burden on users, PCCP allows users to follow the system’s suggestions for a secure password- a feature lacking in most schemes. This technology was fundamentally built to support users in selecting passwords of higher security. Persuasive Cued ClickPoints was compared to text based passwords and two related graphical password systems. Results show that PCCP is effective at reducing hotspots and avoiding patterns formed by click-points within a password, while still maintaining usability. Hotspots are areas of an image that have higher likelihood of being selected by users as password click-points [12].

In Persuasive Cued ClickPoints, a user clicks on one click point on five different images shown in a sequence. The advantage here is; when logging on seeing an image they do not recognize, alerts users that their previous click point was incorrect and users may restart their entry, albeit hotspots have been a perennial problem. The reason why PCCP is effective is because it makes the task of selecting a weak password tedious and time consuming. 

By adding a persuasive feature to CCP, PCCP encourages users to select less predictable passwords and make it more difficult to select passwords where all five click points are hotspots.
Typically, PCCP employs a viewport at the start of the password, when users create a password, the images are slightly shaded except for the viewport. The viewport is positioned randomly rather than specifically to avoid known hotspots, since such information can allow attackers to improve guesses and could lead to the formation of new hotspots. The viewport’s size is intended to offer a variety of distinct points but still cover only an acceptably small fraction of all possible points. The user can press the shuffle button to randomly reposition the viewport and must only select a click-point from within the highlighted viewport. A user can use the shuffle button if he/she is unable to find a memorable point within a current viewport. Random viewport persuades user to choose points at random location, thus increasing the security [23]. 

 
![alt tag](http://doi.ieeecomputersociety.org/cms/Computer.org/dl/trans/tq/2012/02/figures/ttq20120202222.gif)

Viewport highlighting a part of the image


ISSUES WITH TEXT BASED PASSWORDS
Text based passwords are the most popular but have security and usability problems. Alternatives such as biometrics and tokens have their own drawbacks. The perennial problem with text passwords is that it is difficult to effectively authenticate the accuracy of an individual that they are who they say they are. They possess specific pieces of information that can be cracked in minutes. Users often create memorable passwords that are easy for attackers to guess. Logins have been a primary vulnerability [1], [6], [7], [8]. 

More than 95% of the companies have experienced data breaches because of login issues, many big companies like SONY and Target have been a victim. 80% of security breaches were caused by stolen or weak passwords. Organizations must keep it simple and also consider the risks and compromises involved, the ideal solution at hand would be; biometrics, handwritten verification or image-based passwords. Whereas implementing a biometric mechanism turns out to be expensive and inconvenient, handwritten verifications have their own problem with signature forging. Image-based passwords seem to be the most feasible solution as they are designed to try to make passwords more memorable and easier for people to use and therefore more secure. Using a graphical password, users click on images rather than typing alphanumeric characters [2], [3].  

Text-based passwords Vs PCCP 
Theoretical Password Space (TPS): Total number of unique passwords that can be generated according to system specification. 
TPS for text passwords;   95n       95- Number of type able characters on US keyboard
				     n - Length of password.

TPS for PCCP; (w*h/t2)c             w*h - size of image in pixel
				     t2 - Size of tolerance square
				     c - Number of click points
The common security goal is to maximize the effective password space and PCCP here does that quite well compared to text based passwords [23].  
 

ANALYSIS OF PASSWORD DISTRIBUTION
Click-Point Clustering
To analyse the randomness and clustering of 2D spatial data across users, we turned to point pattern analysis commonly used in biology and earth sciences. The analysis used spatstat, a spatial statistics package for the R programming language [17], [18].

The J-statistic from spatial analysis was used to measure clustering of click-points within datasets (formation of hotspots). The J-statistic combines nearest neighbour calculations and empty space measures for a given radius r to measure the clustering of points. 
J~0; all data points cluster at the exact same coordinates.
J=1; dataset is randomly dispersed.
J>1; points are increasingly regularly distributed.
J(r) =1; desirable, since this would be least predictable by attackers.

To compare sets of J-statistics to each other, we employed the following technique. Regarding the data as categorical, six categories stemming from possible orderings are identified: PCCP-CCP-PP, PCCP-PP-CCP, PP-PCCP-CCP, PP-CCP-PCCP, CCP-PCCP-PP, CCP-PP-PCCP. 
The figure below shows the ordering for each of the 17 images. The 3 lab studies were compared and the results showed that PCCP lab approaches complete spatial randomness for all 17 images (near J=1) and is thus much more random than the CCP lab and PP lab datasets [2]. 

![alt tag](https://www.computer.org/cms/Computer.org/dl/trans/tq/2012/02/figures/ttq20120202224.gif)

Two Week Recall Studies
PCCP used 465 images, including the 17 core images. Since participants only had six accounts and PassPoints has only one image per password, six of the 17 core images were used for the PassPoints study. PCCP 2week, this study had 82 participants. Besides testing PCCP under its canonical configuration, we examined the effects increasing the theoretical password space by increasing image size and number of click-points per password. A between-subjects design was used, and participants were randomly assigned to one of six conditions: S5 (small image, five click-points); S6 (small image, six click-points); S7 (small image, seven click-points); L5 (large image, five click-points); L6 (large image, six clickpoints); and L7 (large image, seven click-points). The small images were 451 x 331 pixels and the large, 800 x 600 pixels
(Standardizing to a 4:3 aspect ratio) [4].

The data were used in two separate analysis. First, we compared the S5 condition to the other schemes as its configuration directly matched that of the other studies. Second, we compared the six experimental conditions to each other to investigate the effects of increasing the theoretical password space. PassPoints 2week, this study had 32 participants who created 192 passwords in total; not everyone completed the second session. Session 1 was completed by 32 participants, 11 of whom completed the two-week recall session. Session 2 was added to the methodology after examining the initial results for multiple password interference. Participants recruited after this methodology change completed Session 2 [3].
Text 2week study, thirty four participants took part in this study and created 204 text passwords. Fifteen participants completed the two-week recall session. As in the above study, Session 2 was added after initial analysis of password interference and was only available to participants recruited after this methodological change. The text password system enforced an eight-character minimum, with no other restrictions, giving a theoretical space of 252. While this exceeds that for the compared graphical password schemes, we knew that the effective password space for text systems is often significantly reduced by predictable password choices. We thus expected weak text password choices and potential reuse of passwords across accounts, resulting in a significantly reduced memory load, and chose this larger theoretical password space to avoid an unfair memorability comparison. The figure below shows the interface for the two image sizes. The small and large image conditions shared images resized to different dimensions. The viewport was 75 x 75 pixels [3], [14].

![alt tag](http://doi.ieeecomputersociety.org/cms/Computer.org/dl/trans/tq/2012/02/figures/ttq20120202222.gif)

User interface for password creation for the small and large image sizes in PCCP 

PCCP SECURITY
Guessing Attack
Most basic attack is brute force attack, with expected success after exploring half of the password space (i.e. with a theoretical password space of 243, success after 242 guesses). 

Hotspot Attack With All Server-Side Information
PassPoints passwords from a small number of users can be used to determine likely hotspots on an image, which can then be used to form an attack dictionary. Up to 36% of passwords on the pool image (one of the 17 core images) were correctly guessed with a dictionary of 232 entries [19].

Let us assume in the worst case that attackers gain access to all server side information: Username, user-specific seed, image-identifiers, images, hashed-user password. An analysis was done in this aspect using data on the 17 core images. For each of the 95 user passwords involving solely these images, used as target passwords to find, we built a list of the 10 largest hotspots for each of the 17 images, using all PCCP labs and PCCP 2week-S5 data. These hotspot lists were combined to form a guessing dictionary containing 237 entries for the 17 images. None of the 95 passwords appeared in the dictionary, indicating that no password in our collected data consisted entirely of top-10 hotspots.   

The attacker’s task is more difficult for PCCP because not only is the popularity of the hotspots reduced, but the sequence of images must be determined and each relevant image must be collected making a customized attack per user. Other security solutions would be reducing the size of the mouse cursor and dimming the image. Considerably complicated alternative is to make user input invisible to cameras, e.g. by using eye tracking as an input mechanism [20].


PCCP IMPLEMENTATION ISSUES
Variable Number of Click-Points
A possible strategy for increasing security is to enforce a minimum number of click points, but allow users to choose the length of their passwords, similar to minimum text password lengths. The system would continue to show next images with each click, and users would determine at which point to stop clicking and press the login button. Although most users would likely choose the minimum number of click-points, those concerned with security and confident about memorability could set a longer password. 

Malware, Shoulder Surfing and Other Attacks
Capture attack occurs when attackers directly obtain passwords by intercepting user-entered data, or by tricking users into revealing their passwords. For systems like PCCP, CCP and PassPoints capturing one login instance allows fraudulent access by simple replay attack. 
Shoulder Surfing: The practice of spying on the user of a computer or other electronic devices in order to obtain their personal access information. PCCP is susceptible to shoulder surfing albeit no published empirical study has examined the extent of the threat [24].

Malware is a major concern for text as well as graphical passwords, since keylogger, mouse logger and screen scraper malware could capture data remotely or otherwise make it available to an attacker. Graphical passwords can also be shared by taking photos, capturing screenshots, drawing, although requiring more effort than for text passwords. 

It is seen that hotspots and patterns reduce the security of click based graphical passwords, as attackers can use skewed password distribution to predict and prioritize higher probability passwords for more successful guessing attacks. Visual attention research shows that different people are attracted to the same predictable areas of an image. So, if users select their own click based graphical passwords without guidance, hotspots will remain an issue [13]. 

Users could use password managers or other such tools but the problems with such tools are that they require additional effort on the part of the users creating passwords and often provide little useful feedback to guide user’s actions. In PCCP, creating a less guessable password (by selecting a click point within the first few system suggested viewport positions) is the easiest course of action. Users still make a choice but are constrained in their selection.   	

Discretization
A prototype moved toward an ecologically valid system taking into account implementation details necessary for a real web-based authentication system. The PCCP Web study was conducted with a web based authentication framework (MVP) especially designed to be deployed and accessed by users in their regular environments. The system is intended to allow authentication to become a secondary task, by supporting primary tasks on real websites that require users to log in as part of the process. The PCCP Web study used modified versions of WordPress blogs and phpBB forums. The modifications were made to locally installed packages, altering the authentication process. A button was included rather than a textbox for password entry; pressing the button opened the authentication window and loaded the PCCP authentication module, which takes the user ID from the website, collects the user’s PCCP password, and returns an encoded password string. The original websites remained responsible for authentication, using the encoded string as they would use an entered text password [15].

Discretization of click-points allows for approximately correct click-points to be accepted by the system without storing exact click-point coordinates in the clear. The prototype discussed above implemented Centered Discretization, wherein an invisible discretization grid is overlaid onto the image, dividing the image into square tolerance areas, to determine whether a login click-point falls within the same tolerance area as the initial click-point. For each click-point, the grid’s position is set during password creation by placing it such that there is a uniform tolerance area centred around the original click-point, by calculating the appropriate (x, y) grid offset (Gx, Gy) (in pixels) from a (0,0) origin at the top-left corner of the image. On subsequent user login, the system uses the originally recorded offsets to position the grid and determine the acceptability of the each login click-point [16].

SUMMARY OF SECURITY ANALYSIS
Since PCCP is a sequence of images rather than a single image, the efficiency of guessing attack is reduced. For capture attacks, PCCP is susceptible to shoulder surfing and malware capturing user input during password entry. Social engineering and Phishing is more difficult for PCCP than for other cued recall graphical password scheme because of PCCP’s multiple images. 

FUTURE OF PERSUASIVE CUED CLICK POINTS
In the light of potential guessing and capture attacks, PCCP is best deployed in systems where offline attacks must involve an online system that can limit the number of guess per account per time period; this limit should include password restarts. Even with account locking after t failed login attempts, defences must throttle such online guessing attacks sufficiently to guard against system wide attacks across w accounts. Since an attack gets t*w guess per time window. All client-server communication should be made securely e.g. through SSL to maintain the secrecy of user click points and images [21]. 


CONCLUDING REMARKS
➢	Common security goal in password based authentication systems is to maximize the password space; in PCCP the effective password space has been maximized. 
➢	PCCP’s viewport cannot be exploited during an attack.
➢	At some cost the number of shuffles could be limited for the users, thereby again improving the security. 
➢	Providing instructions, on creating secure passwords, using password managers or providing tools such as strength meters for passwords have only had limited success [22].
➢	PCCP is still susceptible to issues like shoulder surfing, capturing screenshots or taking photos.  

BIBLIOGRAPHY
1.	Article: Vulnerability of login credentials at the heart of cyber hacks and data breaches.
2.	On-Air News: CBS News, 60 Minutes, Season 47, episode 11, first aired 1 December 2014
3.	News Show: Brown Pamela; Jim Sciutto, Evan Perez; Jim Acosta; Eric Bradner, “Investigators Think Hackers Stole Sony Passwords,” CNN Politics, 19 December 2014
4.	E. Stobert, A. Forget, S. Chiasson, P. van Oorschot, and R. Biddle, “Exploring Usability Effects of Increasing Security in Click-Based Graphical Passwords,” Proc. Ann. Computer Security Applications Conf. (ACSAC), 2010.
5.	S. Chiasson, P. van Oorschot, and R. Biddle, “Graphical Password Authentication Using Cued Click Points,” Proc. European Symp. Research in Computer Security (ESORICS), pp. 359-374, Sept. 2007.  
6.	L. Jones, A. Anton, and J. Earp, “Towards Understanding User Perceptions of Authentication Technologies,” Proc. ACM Workshop Privacy in Electronic Soc., 2007. 
7.	L. O’Gorman, “Comparing Passwords, Tokens, and Biometrics for User Authentication,” Proc. IEEE, vol. 91, no. 12, pp. 2019-2020, Dec. 2003. 
8.	A. Jain, A. Ross, and S. Pankanti, “Biometrics: A Tool for Information Security,” IEEE Trans. Information Forensics and Security (TIFS), vol. 1, no. 2, pp. 125-143, June 2006. 
9.	D. Nelson, V. Reed, and J. Walling, “Pictorial Superiority Effect,” J. Experimental Psychology: Human Learning and Memory, vol. 2, no. 5, pp. 523-528, 1976.  
10.	E. Tulving and Z. Pearlstone, “Availability versus Accessibility of Information in Memory for Words,” J. Verbal Learning and Verbal Behavior, vol. 5, pp. 381-391, 1966. 
11.	S. Wiedenbeck, J. Waters, J. Birget, A. Brodskiy, and N. Memon, “PassPoints: Design and Longitudinal Evaluation of a Graphical Password System,” Int’l J. Human-Computer Studies, vol. 63, nos. 1/2, pp. 102-127, 2005.  
12.	B. Fogg, Persuasive Technologies: Using Computers to Change What
We Think and Do. Morgan Kaufmann Publishers, 2003. 
13.	J. Wolf, “Visual Attention,” Seeing, K. De Valois, ed., pp. 335-386,
Academic Press, 2000.  
14.	M. Weir, S. Aggarwal, M. Collins, and H. Stern, “Testing Metrics for Password Creation Policies by Attacking Large Sets of Revealed Passwords,” Proc. ACM Conf. Computer and Comm. Security (CCS), 2010.  
15.	S. Chiasson, C. Deschamps, E. Stobert, M. Hlywa, B. Freitas Machado, A. Forget, N. Wright, G. Chan, and R. Biddle, “ [Short Paper] The MVP Web-Based Authentication Framework,” Proc. Financial Cryptography and Data Security (FC), LNCS, 2012. 
16.	S. Chiasson, J. Srinivasan, R. Biddle, and P.C. van Oorschot, “Centered Discretization with Application to Graphical Passwords,” Proc. USENIX Workshop Usability, Psychology, and Security (UPSEC), Apr. 2008.  
17.	P. Diggle, Statistical Analysis of Spatial Point Patterns. Academic Press, 1983.  
18.	A. Baddeley and R. Turner, “Spatstat: An R Package for Analysing Spatial Point Patterns,” J. Statistical Software, vol. 12, no. 6, pp. 1- 42, 2005.   
19.	P.C. van Oorschot and J. Thorpe, “Exploiting Predictability in Click-Based Graphical Passwords,” J. Computer Security, vol. 19, no. 4, pp. 669-702, 2011.  
20.	A. Forget, S. Chiasson, and R. Biddle, “Shoulder-Surfing Resistance with Eye-Gaze Entry in Click-Based Graphical Passwords,” Proc. ACM SIGCHI Conf. Human Factors in Computing Systems (CHI), 2010.  
21.	B. Pinkas and T. Sander, “Securing Passwords against Dictionary Attacks,” Proc. Ninth ACM Conf. Computer and Comm. Security (CCS), Nov. 2002.   
22.	D. Florencio and C. Herley, “A Large-Scale Study of WWW Password Habits,” Proc. 16th ACM Int’l World Wide Web Conf. (WWW), May 2007.  
23.	Internet: www.cse.iitd.ernet.in  
24.	Internet: www.wikipedia.com 

