<!-- Word replacement api on AWS cloud: See: https://github.com/rajgaurav603/deloitte-api-replace-word/blob/main/api-lambda-word-replace-cfstack.yaml -->
<a name="readme-top"></a>


<!-- TABLE OF CONTENTS -->
<details>
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#about-the-project">About The Project</a>
      <ul>
        <li><a href="#built-with">Built With</a></li>
      </ul>
    </li>
    <li>
      <a href="#getting-started">Getting Started</a>
      <ul>
        <li><a href="#prerequisites">Prerequisites</a></li>
        <li><a href="#installation">Installation</a></li>
      </ul>
    </li>
    <li><a href="#usage">Usage</a></li>
    <li><a href="#roadmap">Roadmap</a></li>
    <li><a href="#contributing">Contributing</a></li>
    <li><a href="#license">License</a></li>
    <li><a href="#contact">Contact</a></li>
    <li><a href="#acknowledgments">Acknowledgments</a></li>
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

1. version control system containing the source : 
2. URL on which the API is accessible : 

<p align="right">(<a href="#readme-top">back to top</a>)</p>

### Tools Used

Following tools and services are used to build this project

* [AWS API Gateway](https://aws.amazon.com/api-gateway/)
* [AWS Lambda](https://aws.amazon.com/lambda/)
* [AWS Code Pipeline](https://aws.amazon.com/codepipeline/)
* [AWS CloudFormation](https://aws.amazon.com/cloudformation/)
* [AWS SNS](https://aws.amazon.com/sns)
* [Github](https://github.com)
* [Postman.com](https://www.postman.com)

<p align="right">(<a href="#readme-top">back to top</a>)</p>


<!-- GETTING STARTED -->
## Getting Started
Please follow the below steps to deploy the project

### Prerequisites
* Create an AWS account
* Create an account on [Postmaster.com](https://www.postman.com)

### How to deploy

Please follow the below steps to deploy the api project on AWS

1. Login to [aws console](https://aws.amazon.com/console/)
2. Go to CloudFormation
3. Click --> create stack -->upload a template file --> upload the yaml file at [cloudformation stack](https://github.com/rajgaurav603/deloitte-api-replace-word/blob/main/api-lambda-word-replace-cfstack.yaml)
4. Enter stack name --> modify parameters if required -->next --> next --> create stack
5. The cloudformation stack will be created
6. Go to output section --> copy apiGatewayInvokeURL value
7. Go to [Postman.com](https://www.postman.com) --> login
8. click on new request  --> select POST method 
9. In 'Enter request url', enter the api link copied from output of cloudformation stack
10. click on 'body'--> click on 'raw'
11. Enter the below string to check api: 
   ```
   {"input_string" : "I like the work culture of Deloitte. Google, Microsoft, Oracle and Amazon are also good organizations."}
   ```
13. Click on Send
14. The api response will appear in the response box below with replaced words.
15. 

<p align="right">(<a href="#readme-top">back to top</a>)</p>


<!-- USAGE EXAMPLES -->
## Usage

Use this space to show useful examples of how a project can be used. Additional screenshots, code examples and demos work well in this space. You may also link to more resources.

_For more examples, please refer to the [Documentation](https://example.com)_

<p align="right">(<a href="#readme-top">back to top</a>)</p>



<!-- ROADMAP -->
## Roadmap

- [x] Add Changelog
- [x] Add back to top links
- [ ] Add Additional Templates w/ Examples
- [ ] Add "components" document to easily copy & paste sections of the readme
- [ ] Multi-language Support
    - [ ] Chinese
    - [ ] Spanish

See the [open issues](https://github.com/othneildrew/Best-README-Template/issues) for a full list of proposed features (and known issues).

<p align="right">(<a href="#readme-top">back to top</a>)</p>


<!-- CONTACT -->
## Contact

Raj Gaurav - [@rajgaurav603](https://www.linkedin.com/in/raj-gaurav-b0a93a8b/) - rajgaurav603@gmail.com

Project Link: [https://github.com/your_username/deloitte-api-replace-word/](https://github.com/rajgaurav603/deloitte-api-replace-word)

<p align="right">(<a href="#readme-top">back to top</a>)</p>



<!-- ACKNOWLEDGMENTS -->
## Acknowledgments

Use this space to list resources you find helpful and would like to give credit to. I've included a few of my favorites to kick things off!

* [Choose an Open Source License](https://choosealicense.com)

<p align="right">(<a href="#readme-top">back to top</a>)</p>



