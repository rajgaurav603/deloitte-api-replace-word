<!-- Word replacement api on AWS cloud: See: https://github.com/rajgaurav603/deloitte-api-replace-word/blob/main/api-lambda-word-replace-cfstack.yaml -->
<a name="readme-top"></a>


<!-- TABLE OF CONTENTS -->
<details>
  <summary>Table of Contents</summary>
  <ol>
    <li><a href="About The Project">About The Project</a></li>
    <li><a href="Deliverables">Deliverables</a></li>
    <li><a href="Tools Used">Tools Used</a></li>
    <li>
      <a href="Deployment">Deployment</a>
      <ul>
        <li><a href="Prerequisites">Prerequisites</a></li>
        <li><a href="How to deploy">How to deploy</a></li>
        <li><a href="Testing the api">Testing the api</a></li>
      </ul>
    </li>
    <li>
      <a href="Automating release and updates">Automating release and updates</a>
      <ul>
        <li><a href="Create a AWS codepipeline">Create a AWS codepipeline</a></li>
        <li><a href="Adding notification rule">Adding notification rule</a></li>
      </ul>
    </li>
    <li><a href="Contact">Contact</a></li>
  </ol>
</details>


<!-- ABOUT THE PROJECT -->
## About The Project

1. Build an API that will use a string as input and does a find and replace for certain words and outputs the result. 
For example: replace Google for Google©. 

2. The words that need to be replaced are listed below:
* Oracle -> Oracle©
* Google -> Google©
* Microsoft -> Microsoft©
* Amazon -> Amazon©
* Deloitte -> Deloitte©

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Deliverables

1. version control system containing the source : [Github Link](https://github.com/rajgaurav603/deloitte-api-replace-word)
2. URL on which the API is accessible : https://fzhq3vslv0.execute-api.ap-south-1.amazonaws.com/live/api

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Tools Used

Following tools and services are used to build this project

* [AWS API Gateway](https://aws.amazon.com/api-gateway/)
* [AWS Lambda](https://aws.amazon.com/lambda/)
* [AWS Code Pipeline](https://aws.amazon.com/codepipeline/)
* [AWS CloudFormation](https://aws.amazon.com/cloudformation/)
* [AWS SNS](https://aws.amazon.com/sns)
* [Github](https://github.com)
* [Postman.com](https://www.postman.com)

<p align="right">(<a href="#readme-top">back to top</a>)</p>


<!-- Deployment -->
## Deployment
Please follow the below steps to deploy the project

### Prerequisites
* Create an AWS account [AWS Acccount Sign up](https://portal.aws.amazon.com/billing/signup?nc2=h_ct&src=header_signup&refid=09863622-0e2a-4080-9bba-12d378e294ba&redirect_url=https%3A%2F%2Faws.amazon.com%2Fregistration-confirmation#/start/email)
* Create an account on [Postmaster.com](https://www.postman.com)

### How to deploy

Please follow the below steps to deploy the api project on AWS

1. Login to [aws console](https://aws.amazon.com/console/)
2. Go to CloudFormation
3. Click --> create stack -->upload a template file --> upload the yaml file at [cloudformation stack](https://github.com/rajgaurav603/deloitte-api-replace-word/blob/main/api-lambda-word-replace-cfstack.yaml)
4. Enter stack name --> modify parameters if required --> next --> next --> create stack
5. The cloudformation stack will be created
6. Go to output section --> apiGatewayInvokeURL value is the api key link

### Testing the api
1. Go to [Postman.com](https://www.postman.com) --> login
2. click on new request  --> select POST method 
3. In 'Enter request url', enter the api link copied from output of cloudformation stack
4. click on 'body'--> click on 'raw'
5. Enter the below string to check api: 
   ```
   {"input_string" : "I like the work culture of Deloitte. Google, Microsoft, Oracle and Amazon are also good organizations."}
   ```
6. Click on Send
7. The api response will appear in the response box below with replaced words.

<p align="right">(<a href="#readme-top">back to top</a>)</p>


<!-- Automating deployment -->
## Automating release and updates
Create AWS codepipeline for continuous delivery and to automate release.

### Create a AWS codepipeline 
1. Click on create pipeline
2. Enter pipeline name
3. Add an service IAM role with sufficient permissions to deploy the stack --> click next
4. select "github(version 1)" in source provider --> click on connect to github --> enter github credentials
5. select repository "rajgaurav603/deloitte-api-replace-word"
6. select branch "main"
7. For Change detection options, select "GitHub webhooks"
8. click on skip build stage
9. In Deploy provider select "AWS cloudformation"
10. In action mode select "create or update stack"
11. select stack name
12. In ArtifactName select "sourceArtifact"
13. In filename enter "api-lambda-word-replace-cfstack.yamlselect"
14. Select CAPABILITY_IAM in capabilities
15. choose role name --> click next
16. Review and create pipeline

Now the pipeline will be triggered every time the yaml file is updated in github.


<p align="right">(<a href="#readme-top">back to top</a>)</p>

### Adding notification rule
1. Click on Create notification rule
2. Enter notification name
3. choose "basic" details
4. Under "Events that trigger notifications" select pipeline execution :succeeded and failed
5. Under targets select SNS topics --> SNS topic name 
6. Click on Submit

Add email id to subscribe to SNS topic and confirm the subscription to receive emails on pipeline execution.

<!-- CONTACT -->
## Contact

Raj Gaurav - [linkedin](https://www.linkedin.com/in/raj-gaurav-b0a93a8b/) - rajgaurav603@gmail.com

Project Link: [https://github.com/your_username/deloitte-api-replace-word/](https://github.com/rajgaurav603/deloitte-api-replace-word)

<p align="right">(<a href="#readme-top">back to top</a>)</p>





