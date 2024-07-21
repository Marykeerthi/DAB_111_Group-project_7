# DAB_111_Group-project_7


## INFORMATION OF THE DATASET

Title of Dataset: "Salary of Data Professions" 
Website used for Data collection:"Kaggle"
https://www.kaggle.com/datasets/krishujeniya/salary-prediction-of-data-professions

Number of variables: 8

Number of rows: 50

Variable List:
EMPLOYEEID: Unique EmployeeID of the employees 
NAME: Name of the Employees
DOJ: Date of Joining
DESIGNATION:The job role or designation of the data professional
AGE: Age of the professional
DEPARTMENT: Department of the individual employee
PAST EXPERIENCE: If the employee worked previously
SALARY: Current Annual salary of the employee


## METHODOLOGICAL INFORMATION

Description of methods used for collection/generation of data: https://www.kaggle.com/datasets/krishujeniya/salary-prediction-of-data-professions

Methods for processing the data: Reviewed the file and included the variables which are related fully in context of the database.


### IMPORTED NECESSARY MODULES
- Installed 'Pandas', 'Sqlite3' and 'Flask': Three libraries which help to handle the dataframes and databases and to create a website. Flask includes 'werkzeug.serving' method which easily run the website.
- Imported Flask,render_template_string,render_template from Flask module and run_simple from werkzeug.serving: The class 'Flask' is necessary for creating website,while the functions 'render_template_string','render_template' is used to direct raw html file and for importing html file.
'run_simple function is used for developing server which allows to test and run the website. 
- Imported the CSV to read the CSV file.


### CREATED DATABASE
We loaded the data into the database.
- con=sqlite3.connect('professionals.db'): develops a connection to the database('professionals.db'). If the database doesn't exsit, it will create database('professionals.db').
- cursor=con.cursor(): It helps to execute sql commands.
- Created dataframe using sql commands and query.
- with open ("Data.csv") as file:: Opens the Data file.
- csv.reader: helps to read the content in the file.
- if row[0]=='EMPLOYEEID': check whether the first coloumn is "EMPLOYEEID". If yes, then continue which removes the header row from csv data.
- cursor.execute("INSERT INTO Salary_of_professionals VALUES(?,?,?,?,?,?,?,?)",(row[0],row[1],row[2],row[3],row[4],row[5],row[6],row[7])): Insert data into the table.
    -  VALUES(?,?,?,?,?,?,?,?)= Creates new row in the data table. ? are represented as the placeholders for the values that is to be inserted.
    -  (row[0], row[1], row[2], row[3], row[4], row[5], row[6], row[7]): used to insert data in each row of csv file into a database.
-  pd.read_csv: Read the data.
- con.commit(): save the updates in the database
- con.close(): close the connection from the database.


### CREATED WEBSITE 
We presented the data through a website using Flask. We also used HTML and CSS to create an interactive website which displays the database of our data professionals Salary Database.

- webpage=Flask(__name__): This code is used to create an instance named 'webpage' to develope webpages in the web application. 
- @webpage.route('/'): defines the route and access the webpages.
- home(): A function which is used to access content and layout of the home page in the website.
- data_html=df.to_html(index=False): Convert the dataframe into html page.
- Then applied CSS style to the webpage using HTML. Homepage displays salary data table of data professionals.
- @webpage.route('/about'): Defines the route of about page and access the about page.
- about(): A function which is used to access about page. About page shows the source of our data and the describtion of each variable in the data. 
- run_simple('localhost',8500,webpage,use_reloader=False,use_debugger=False): runs the website on localhost.



###### People involved with sample collection, processing, analysis and/or submission:  Mary keerthi Palepu,Malavika pallikkad Raju.


