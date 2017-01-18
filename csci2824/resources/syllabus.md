#Discrete Structures (CSCI 2824, Spring 2017)


###Course Information 

* **Class Date/Time**: MWF 9-9:50am 
* **Class Location**: FLMG 155 
* **Instructor**: Chris Ketelsen 
* **Prerequisites**: 
	* C- or better in Calculus 1 
	* Completion of or concurrent enrollment in Data Structures (CSCI 2270) 
	* _ability to program in some language: preferably Python or C++_ 
* **Office Hours**: 
	* Chris: M 10-11:30am and W 2-3:30pm in ECOT 731 / After class on Fridays if there is interest

###Why Discrete Structures? 

The course covers fundamental ideas from discrete mathematics, especially for computer science students. It focuses on topics that will be foundational for future courses including algorithms, artificial intelligence, programming languages, automata theory, computer systems, cryptography, networks, computer/network security, databases, and compilers.

_Computer Science_ is all about solving interesting problems efficiently and cheaply, using computers! Here are some real problems that keep many computer scientists awake at night:

* Route a packet reliably from one server to another on the internet (faster than [existing protocols](http://en.wikipedia.org/wiki/Routing)? even when routers can fail on us?)
* Search for web pages (better than [Google](http://www.google.com), [Bing](http://www.bing.com) or your favorite search engine??)
* Find the biggest [clique](http://en.wikipedia.org/wiki/Clique) on Facebook. How many people are in this clique? Who are they?
* Understand how to sequence the human genome.
* Find all the prime factors for really large number (> 10^10000).
* Write a program to play _go_ (and play better than the best human champion?).
* Write a program to check if a program is “correct” (keeps your instructor awake at night!).

Some of these problems are [really hard](http://en.wikipedia.org/wiki/NP-complete) to solve using a computer. No one knows if there are easy solutions to these problems and it would be nice to see efficient solutions in this century. In this course, we will cover the mathematical foundations that will help us formulate solutions to some of the real problems above. Specifically, we will learn

* How to abstract using mathematical objects such as sets, relations, functions, trees and graphs.
* How to count really well. 
* How to reason like a _pro_: obtain succinct water-tight proofs to guarantee that your solutions are correct, better than a competing solution and all that.
* We will learn these cool mathematical facts, so that in the course of your education as a computer scientist, you will write cool programs to solve interesting problems involving automated reasoning, games, fractals, social networks and the human genome.

###Topics Covered

Roughly, we will cover the following topics (some of them may be skipped depending on the time available).

* **Logic**: Propositional and First Order Logic, Boolean Algebra.
* **Proofs**: Primer on writing proofs, inductions, proof by contradiction.
* **Sets, Relations and Functions**: Basic properties. Paradoxes in naive set theory. Infinite sets. 
* **Recursion**: Recursive functions and recursively defined structures.
* **Combinatorics**: Counting, binomial theorem, counting with recursion.
* **Discrete Probability**: Basic facts, Bayes Rule 
* **Graphs**: Definitions and properties of graphs.
* **Trees**: Definitions and properties of trees.
* **Example Applications**: Artificial Intelligence (automated reasoning, game playing), Graphics (drawing fractals), Cryptography (RSA) and Networks (social network analysis).

###Textbook 

We will use [_Discrete Mathematics and Its Applications, 7th ed._](https://smile.amazon.com/Discrete-Mathematics-Its-Applications-Seventh/dp/0073383090/ref=sr_1_1?s=books&ie=UTF8&qid=1484628806&sr=1-1&keywords=rosen+discrete+math) by Kenneth H. Rosen.  

I realize the book is pricey, but it's pretty well-written and includes lots of cool computer science applications.  Earlier additions are fine, but you'll be responsible for figuring out the section number map between editions for the daily reading. 

###Coursework 

**Weekly(ish) Homework**: Homework will be assigned roughly every week throughout the course and due at the beginning of class on Friday of the week after it is assigned.  Some assignments will involve written work and small programming tasks. Other assignments will be devoted to exploring specific computer science applications.  These application assignments will **count as two standard assignments**.  **Your two lowest homework scores will be dropped.** You are expected to write up your solutions neatly, with full explanations and justifications. You may discuss problems with your classmates, **but all work must be your own**.  Please be mindful of the due dates as late submissions will not be accepted.  I accept homework at the start of class or underneath my office door prior to the start of class.  I do **NOT** accept emailed homework under any circumstances.

**Examinations**: Every 2-3 weeks there will be a 20-ish minute quiz (a.k.a. _mini-exam_) on material corresponding to the previous set of lectures and homework.  The dates and material for each quiz will be posted well in advance. Your lowest quiz score will be dropped. 

There will be a cumulative final exam during the schedule final exam time-slot. You must take the final exam and score at least a 25% to pass the course. 

**Course Participation**: Occasionally we will solve a short (5-10 minutes) tutorial problem as a class which you will write up and hand in at the end of lecture.  These are mainly designed to make sure you're attending class (_and also awake_).  If you miss a tutorial problem you can make-up some participation points by being active on the class forum (asking meaningful question, helping your classmates, etc). 

###Grade Determination 
The overall grades will be based on a cumulative score computed from 
* The weekly homework (with two scores dropped)
* The grades from quizzes (with one score dropped)
* The score from class participation 
* The final exam 

Overall, the contributions to the final grades will be: 
* Weekly Homework (35% of the grade)
* In-Class Quizzes (35% of the grade)
* Participation (10% of the grade)
* Final Exam (20% of the grade)

Unless adjustments are necessary, letter grades will be assigned using the standard grading scale: 

| Letter | Raw Average |
|--------|-----------|
|     A  |   93-100    |
|     A- |   90-92     |
|     B+ |   87-89     |
|     B  |   83-86     |
|     B- |   80-82     |
|     C+ |   77-79     |
|     C  |   73-76     |
|     C- |   70-72     |
|     D+ |   67-69     |
|     D  |   63-66     |
|     D- |   60-62     |
|     F  |   00-59     |

###Collaboration Policy 

The collaboration policy is pretty simple:

* _Inspiration is free_: you may discuss homework assignments with anyone. You are especially encouraged to discuss solutions with your instructor and your classmates.

* _Plagiarism is forbidden_: the assignments that you turn in should be written entirely on your own. While writing the assignment you are not allowed to consult any source other than the textbook(s) for the class, your own class notes or the lecture slides for the class. Copying/consulting from the solution of another classmate constitutes a violation of the course's collaboration policy and the honor code.

* _Do not search for a solution on-line_: You may not actively search for a solution to the problem from the internet. This includes posting to newsgroup or asking experts at other universities.

* _When in doubt, ask_: If you have doubts about this policy or would like to discuss specific cases, please ask the instructor.

###Standard Course Policies 

<br>

**Honor Code**

All students enrolled in a University of Colorado Boulder course are responsible for knowing and adhering to the [academic integrity policy](http://www.colorado.edu/policies/academic-integrity-policy) of the institution. Violations of the policy may include: plagiarism, cheating, fabrication, lying, bribery, threat, unauthorized access, clicker fraud, resubmission, and aiding academic dishonesty. All incidents of academic misconduct will be reported to the Honor Code Council (honor@colorado.edu; 303-735-2273). Students who are found responsible for violating the academic integrity policy will be subject to nonacademic sanctions from the Honor Code Council as well as academic sanctions from the faculty member. Additional information regarding the academic integrity policy can be found at [honorcode.colorado.edu](http://honorcode.colorado.edu/).

**Disability Accommodations**

If you qualify for accommodations because of a disability, please submit to your professor a letter from Disability Services in a timely manner (for exam accommodations provide your letter at least one week prior to the exam) so that your needs can be addressed. Disability Services determines accommodations based on documented disabilities. Contact Disability Services at 303-492-8671 or by e-mail at [dsinfo@colorado.edu](mailto:dsinfo@colorado.edu). If you have a temporary medical condition or injury, see the [Temporary Injuries](http://www.colorado.edu/disabilityservices/students/temporary-medical-conditions) guidelines under the Quick Links at the [Disability Services](http://www.colorado.edu/disabilityservices/) website and discuss your needs with your professor.


**Religious Observances**

Campus policy regarding religious observances requires that faculty make every effort to deal reasonably and fairly with all students who, because of religious obligations, have conflicts with scheduled exams, assignments, or required attendance. If you have an exam or assignment conflict due to a religious observance please notify me in a timely manner. See the [campus policy regarding religious observances](http://www.colorado.edu/policies/observance-religious-holidays-and-absences-classes-andor-exams) for full details.


**Classroom Behavior**

Students and faculty each have responsibility for maintaining an appropriate learning environment. Those who fail to adhere to such behavioral standards may be subject to discipline. Professional courtesy and sensitivity are especially important with respect to individuals and topics dealing with differences of race, color, culture, religion, creed, politics, veteran's status, sexual orientation, gender, gender identity and gender expression, age, disability, and nationalities. Class rosters are provided to the instructor with the student's legal name. I will gladly honor your request to address you by an alternate name or gender pronoun. Please advise me of this preference early in the semester so that I may make appropriate changes to my records. For more information, see the policies on [classroom behavior](http://www.colorado.edu/policies/student-classroom-and-course-related-behavior) and the [student code](http://www.colorado.edu/osc/sites/default/files/attached-files/studentconductcode_16-17-a.pdf).


**Sexual Misconduct, Discrimination, Harassment and/or Related Retaliation**

The University of Colorado Boulder (CU Boulder) is committed to maintaining a positive learning, working, and living environment. CU Boulder will not tolerate acts of sexual misconduct, discrimination, harassment or related retaliation against or by any employee or student. CU's Sexual Misconduct Policy prohibits sexual assault, sexual exploitation, sexual harassment, intimate partner abuse (dating or domestic violence), stalking or related retaliation. CU Boulder's Discrimination and Harassment Policy prohibits discrimination, harassment or related retaliation based on race, color, national origin, sex, pregnancy, age, disability, creed, religion, sexual orientation, gender identity, gender expression, veteran status, political affiliation or political philosophy. Individuals who believe they have been subject to misconduct under either policy should contact the Office of Institutional Equity and Compliance (OIEC) at 303-492-2127. Information about the OIEC, the above referenced policies, and the campus resources available to assist individuals regarding sexual misconduct, discrimination, harassment or related retaliation can be found at the [OIEC website](http://www.colorado.edu/institutionalequity/).



