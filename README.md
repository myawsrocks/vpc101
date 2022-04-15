[![Contributors][contributors-shield]][contributors-url]
[![Forks][forks-shield]][forks-url]
[![Stargazers][stars-shield]][stars-url]
[![Issues][issues-shield]][issues-url]
[![License][license-shield]][license-url]
<br>
[![VPC 101 on myaws.rocks][website-shield]][website-url]
[![LinkedIn][linkedin-shield]][linkedin-url]
[![Twitter][twitter-shield]][twitter-url]
<!-- PROJECT LOGO -->
<br />
<div align="center">
  <a href="https://github.com/myawsrocks/vpc101">
    <img src="images/minifig.png" alt="Logo" width="80" height="80">
  </a>

<h3 align="center">myaws.rocks vpc 101</h3>

  <p align="center">
    How to build a VPC demo
    <br />
    <br />
    <a href="https://github.com/myawsrocks/vpc101/issues">Report Bug</a>
    ·
    <a href="https://github.com/myawsrocks/vpc101/issues">Request Feature</a>
  </p>
</div>

<!-- TABLE OF CONTENTS -->
<details>
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#about-the-project">About The Project</a>
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
  </ol>
</details>

<!-- ABOUT THE PROJECT -->
## About The Project
This solution walks through the building and securing of the following VPC.<br/>
At the end of the deployment you will have a VPC spanning multiple Availability Zones (AZ) with both IPv4 and IPv6 ranges.<br/>

![Product Name Screen Shot][product-screenshot]

###Components built with the solution are:
<ol>
<li>VPC - vpc_1.yaml</li>
<li>IPv6 Range - vpc_2.yaml</li>
<li>Subnets - vpc_3.yaml</li>
    <ul>
    <li>Public</li>
    <li>Presentation</li>
    <li>Application</li>
    <li>Data</li>
    </ul>
<li>Route Table - vpc_4.yaml</li>
<li>VPC Flow Logs - vpc_5.yaml</li>
<li>VPC Endpoints for AWS Services - vpc_6.yaml</li>
<li>Internet Routing - vpc_7.yaml</li>
    <ul>
    <li>Internet Gateway</li>
    <li>Public NAT Gateway</li>
    <li>Egress Only Internet Gateway:</li>
    </ul>
</ol>
<p align="right">(<a href="#top">back to top</a>)</p>

<!-- GETTING STARTED -->
## Getting Started
### Prerequisites
To keep things simple this is a single file CloudFormation template to deploy all components.
As such this can be uploaded directly into the AWS console so no need to have any fancy deployment tools.
1. An AWS Account
2. An IAM User with rights to deploy cloudformation and create resources.
3. A copy of the code.
#### AWS Account
If you don't already have an AWS account you can [sign up here.](https://portal.aws.amazon.com/billing/signup) </br>
**Don't forget to secure your new account!!</br>**
If you don't know how take a look at my post on [setting up your AWS account](https://myaws.rocks/setting-up-your-aws-account/)
#### IAM User
If you didn't follow my post and are logging in with root go and create an IAM user.</br>
Details on how are in the [AWS IAM UserGuide](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_users_create.html#id_users_create_console)
### Code
The simplest way to get the code is to [download the zip file](https://github.com/myawsrocks/vpc101/archive/refs/heads/main.zip) and extract it using your pc's built in zip program to a location you can easily get to.<br/>
If your more advance clone the repo:
Clone the repo
   ```sh
   git clone https://github.com/myawsrocks/vpc101.git
   ```
### Deployment
If you just want to deploy the full VPC, create a new stack with the [vpc.yaml](vpc.yaml) file.<br/>
You can chose to enter custom parameters but the solution will build with defaults.<br/>
</br>
If you are following along with my blog and/or want to build components step by step first create a new stack with the [vpc_1.yaml](vpc_1.yaml) file.<br/>
Again you can chose to enter custom parameters but the solution will build with defaults.<br/>
Use the "Update Stack" option and upload the next file (vpc_2.yaml then vpc_3.yaml etc) to go through and build the components.
### Clean Up
<div class="warning" style='background-color:#ffa666'>
<h2 style='text-align:center'>WARNING!</h2>
<h4 style='text-align:center'>Most components of the VPC have no cost.<br/>However NAT gateways are one of the 3 exception!</h4>
<p style='margin-left:1em'>
Dependant on region they can cost between 4¢ and 7¢ an hour.<br/>
While this might not seem much if you deploy in 3AZs (good practice) this is upto 21¢ and hour.<br/>
So in a month with 31 days (744 hours) that equates to <b>$157</b> just to have them provisioned.<br/>
<br/>
</p>
</div>
So, once you've taken a look around what's been provisioned go back to the cloudformation stack and delete. 

<p align="right">(<a href="#top">back to top</a>)</p>
<!--USAGE EXAMPLES
## Usage

Use this space to show useful examples of how a project can be used. Additional screenshots, code examples and demos work well in this space. You may also link to more resources.

_For more examples, please refer to the [Documentation](https://example.com)_

<p align="right">(<a href="#top">back to top</a>)</p>
-->
<!-- ROADMAP -->
## Roadmap

- [ ] Alternate NAT options
  - [ ] EC2 based NAT
  - [ ] Reduced redundancy NAT Gateway
  - [ ] Reduced redundancy EC2 based NAT
- [ ] IPv6 only subnets
  - [ ] 

See the [open issues](https://github.com/myawsrocks/vpc101/issues) for a full list of proposed features (and known issues).

<p align="right">(<a href="#top">back to top</a>)</p>
<!-- CONTRIBUTING -->
## Contributing

Contributions are what make the open source community such an amazing place to learn, inspire, and create. Any contributions you make are **greatly appreciated**.

If you have a suggestion that would make this better, please fork the repo and create a pull request. You can also simply open an issue with the tag "enhancement".
Don't forget to give the project a star! Thanks again!

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request
6. 
<p align="right">(<a href="#top">back to top</a>)</p>
<!-- LICENSE -->

## License
Distributed under the GPL3 License. See [license file](LICENSE) for more information.

<p align="right">(<a href="#top">back to top</a>)</p>


<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->
[contributors-shield]: https://img.shields.io/github/contributors/myawsrocks/vpc101.svg?style=plastic&logo=appveyor
[contributors-url]: https://github.com/myawsrocks/vpc101/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/myawsrocks/vpc101.svg?style=plastic&logo=appveyor
[forks-url]: https://github.com/myawsrocks/vpc101/network/members
[stars-shield]: https://img.shields.io/github/stars/github_username/repo_name.svg?style=plastic&logo=appveyor
[stars-url]: https://github.com/myawsrocks/vpc101/stargazers
[issues-shield]: https://img.shields.io/github/issues/github_username/repo_name.svg?style=plastic&logo=appveyor
[issues-url]: https://github.com/myawsrocks/vpc101/issues
[license-shield]: https://img.shields.io/github/license/github_username/repo_name.svg?style=plastic&logo=appveyor
[license-url]: https://github.com/myawsrocks/vpc101/blob/master/LICENSE
[linkedin-shield]: https://img.shields.io/badge/-LinkedIn-black.svg?style=social&logo=linkedin&color=blue
[linkedin-url]: https://linkedin.com/in/robinwford/
[twitter-shield]: https://img.shields.io/twitter/follow/robinwford?color=blue&logo=twitter&style=social
[twitter-url]: https://twitter.com/robinwford
[website-url]: https://myaws.rocks/aws-vpc-101
[website-shield]: https://img.shields.io/badge/Project%20Link-myaws.rocks%20VPC101-yellowgreen?style=social
[product-screenshot]: images/VPC.jpg