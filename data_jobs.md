# Data jobs and why what you need is probably not a data scientist

This is a biased summary in case all you know about those comes from the popularity contest between a glass wearing sexy data scientist and a shiny humanoid robot on the covers of your favorite magazine these past years.

![Drake Hotline Bling meme describing how instead of understanding data needs, a marketing victim will just hire a data scientist.](https://i.imgur.com/5bEDDYo.png)

These jobs are confusing and blurry for everyone, even when you occupy one of them. So I'll try my best at explaining the ones I have occupied or worked with:

- data engineer
- data architect
- data analyst
- business intelligence (BI) engineer
- data scientist
- machine learning (ML) engineer

## Data Engineer

The data engineer is able to reach the data from the depth of your backend severs and make them accessible, using a variety of tech tools that includes coding.

He can collect and centralize data in one place called the "data lake" where it is not yet well organized. The next part of his job is to organize this data into a "data warehouse". The data warehouse is designed according to the technical requirements of business needs, using well thought data schema (picking the relevant fields), optimizations (data queried together should be stored together), orchestrations (how fresh should the data be?), quality tests (are we sure the data is correct?) and more.

A data engineer may also be able to use big data tools (Apache Hadoop, Apache Spark, Apache Kafka...) but note that this is not necessary as most companies do not need the big data tools complexity most of the time. Today, all the big cloud providers (AWS, GCP, Azure) give access to very efficient tools to tackle data engineering problems at a fraction of the administration work required for a Hadoop cluster.

Once the data engineer job is done, the data should be much more easily accessible to the colleagues, sometimes through graphical user interfaces, but more often through still quite technical means such as the SQL language (the common way to query databases) or an internal API (an interface made for programs rather than humans).


## Data Architect

A data architect is to a data engineer what a software architect is to a software engineer: an experienced engineer that focuses on the early stage of projects.

His experience allows him to take structuring decisions about the data architecture: which data tools should be used and how they should be connected to respond to the technical challenges of the project.

In a small team with one data engineer, the data engineer will assume this responsibility, but once the team starts growing, it may make sense to have the most experienced, or willing one, focus more on data architecture.


## Data Analyst

The data analyst answers the "business questions" (a generic way to call the final data user's need, not necessarily business) using data, for example: how many new paying customers did we have yesterday? how much time is there on average between a first contact and a first payment?

The data analyst generally isn't a technician that will code programs, he relies on more approachable aggregated tables and graphical interfaces (Qlik, Tableau, PowerBI...) to find his answers. Some more technical data analysts may use SQL which allows them to fetch data earlier in the data pipelines created by the data engineer.

The data analyst needs to be close to the final data user in order to correctly understand the need, thus he's often part of a business team rather than a tech team. For example, a member of the marketing, product, or finance team spending half of his time looking at graphs and tables is a part-time data analyst.


## BI Engineer

The business intelligence engineer is probably the oldest existing job name among the ones I'm describing. It existed before the big data revolution (seminal articles published from 2003 by web giants) that created the newer data engineer and data scientist professions.

Answering questions with data was of course already a common thing in data based businesses such as banking and insurance, so the BI engineer was and may still be the one for this purpose, assuming a position that I place between a data engineer and a data analyst.

As I consider that the backend coding part is for the data engineer, the BI engineer is the one that will design and create the final steps between the data warehouse (organized but technical access) and the interface for a final non-technical user. For example it can be designing and feeding analytical processing tools (OLAP), dashboards, spreadsheets and reports that will be used by data analysts.

Some companies also have BI developers or BI analysts that I'd associate respectively with data engineers and data analysts.


## Data Scientist

![Stereotypical image of a humanoid robot with floating symbols to represent AI.](https://i.imgur.com/OEjxMYb.png)

The data scientist shines when questions or product features cannot be covered anymore by a data analyst using straight forwards visualizations and tables.

He's able to use advanced statistics and advanced algorithms (such as machine learning) to answer those complex questions. The data scientist opens a whole new category of data usage called prediction. For example by attributing a score to a user, the data scientist may predict if he's going to be a spammer or a big paying client before he actually starts to spam or pay. 

The data scientist generally relies on technically accessible data that has been prepared by the data engineer. Unless there is no data engineer available in this case he will have to do the data engineering, but this is not where he is the most valuable.


## ML Engineer

A data scientist generally works in a development or a sandbox environment where he can freely explore the data and test algorithms. Once the algorithm is picked and the model is trained (that's the learning part), deploying it to production, where the clients are, and making sure it remains relevant as time flows, represents a very different kind of challenge.

This is where the data scientist may stop and the machine learning engineer starts.

The machine learning engineer has a good understanding of machine learning algorithms, but he is specialized in the engineering required for the data scientist's work to correctly run live.


## Nuances

As you noticed, definitions are not that precise, there's a lot of overlapping and they will vary depending on the company.

The overlapping is the reality at most small/medium companies, where one data engineer or one data scientist or one BI engineer... may be doing the job of 3 or 4 different professions. I'd recommend taking good care of employees who are able to accomplish such a feat. At the opposite in huge GAFAM like companies, data jobs may be ultra specialized, for example a data engineer may only be designing SQL queries to transfer data between the data lake and the data warehouse.

Some people tend to include all of these professions into the term data scientist as if it was a generic term encompassing everything. I do not think it is fitting, and I have first hands experience of the misunderstandings it may produce at companies when they are recruiting and for employees when they are recruited.


## What you need is probably not a data scientist

This is provocative on purpose, yes, some companies do need those machine learning based predictions, but:

- If you don't yet have the equivalent of a data lake and/or a data warehouse, and you hire a data scientist then the data scientist will spend most, or his entire time, doing data engineering so he has the necessary data to work on his algorithms. As I said above, this is not where a data scientist shines. ==> What you need is a data engineer and/or a data architect!
- Most business questions do not require advanced algorithms, even when companies are convinced of the opposite because they have been influenced by the data science marketing bulldozer. Most of these questions can be answered with aggregation tables and visualizations. ==> If point 1 is already covered by your data engineer, then what you need is a data analyst and/or a BI engineer!

As a summary, a logical data team recruitment order would be:

- Data engineer / data architect: to collect, centralize, organize and make the data accessible according to technical requirements.
- Data analyst / BI engineer: to answer most of your business questions.
- Data scientist: if questions remain so you need advanced statistics and predictions.
- ML engineer: when you start to have a couple of data science projects that you want to see reliably running in production.

![Positioning the data jobs on a two axes diagram, x: data project timeline, y: bottom towards backend top towards final users](https://i.imgur.com/qSjKi7L.png)

Please leave a comment if you agree or disagree with me, I'm always happy to discuss and progress!

nicolas dot parot dot alvarez at gmail

CC-BY 4.0 Nicolas Parot Alvarez on the text, meme derivative and diagram

Originally posted here: https://www.linkedin.com/pulse/data-jobs-why-what-you-need-probably-scientist-nicolas-parot-alvarez/
