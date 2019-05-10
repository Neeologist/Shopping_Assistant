# Graph_Chatbot_recommendation
This is a graph data base with production recommendation engine and chatbot embeded in the website.
For this demo, you will need:
1. Neo4j server host (e.g. graphenedb:https://www.graphenedb.com/)
2. Google Dialogflow account (https://console.dialogflow.com)
3. AWS account for website hosting (https://aws.amazon.com/)

# Follow the steps
# Database setup
1. Import the graph.db (GraphDB folder) into your neo4j local or server host (using graphenedb: https://www.graphenedb.com/). Get the connection details, url: http://localhost:7474 (if local host), username, password.
2. open index.html, input the url, username, password, click run. You can see the nodes and relationships showing.

# Chatbot setup
Here the chatbot NLP is using Google dialogflow, you need to open an account if you don't have one. And also the chatbot front-end is using facebook messenger.

1. Create an agent, and in settings->Export and Import, select restore from zip, and upload the chatbot zip file (Dialogflow folder).
2. Next, click integrations, and choose facebook messenger, follow the steps: https://cloud.google.com/dialogflow-enterprise/docs/integrations/facebook
3. Assume you successfully finish last step, and have set up a fb page for messenger. Open the page you have created, click "About", get the Page ID (e.g. 90322901293029). 
4. Open the facebook for developer page (this should also be created by step 2), get the App ID (e.g. 198849832991) for the messenger.

# Connection between the index webpage and fb messenger
1. run the index.html (including related folder and files) on AWS (know how to set up a website using EC2 https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/CHAP_Tutorials.WebServerDB.CreateWebServer.html). Get the public url (e.g. http://ec2-*-*-***-***.us-east.compute.amazonaws.com/), which will be the third-party domains that are accessible in the Messenger web view for use with the Messenger extensions SDK and for Messenger plugins.
2. Open the fb page for messenger (same as chatbot setup step 2,3), go to settings->Messenger Platform->White-listed domains, type into the public url from (step1).
3. Access the public url, you will get a graph showing with chatbot embeded in.

