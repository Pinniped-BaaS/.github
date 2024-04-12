# Overview
An open source backend that prioritizes on being portable, extensible, and easy to use. Pinniped is built with JavaScript to deliver a backend that offers:
* Auto-generated REST APIs,
* Admin dashboard for monitoring,
* SDK for frontend development,
* An embedded database (SQLite3).

## Getting Started
### Prerequisites
To create a Pinniped application the following must be installed:
* Node.js

Once Node.js is installed, you can create a Pinniped application through its CLI tool.

### Install the CLI
To install the CLI tool, you can use the built-in package manager `npm`.

Run `npm install pinniped-cli -g`.

### Create a Pinniped Application
1. Go to the directory where you'd like to create your application.
2. Run `pinniped create`.

### Deploy a Pinniped Application
First, you need to set up your AWS CLI tool. The instructions can be found [here](https://docs.aws.amazon.com/cli/latest/userguide/sso-configure-profile-token.html#sso-configure-profile-prereqs).

1. Optional: update the variables in the given `.env` file if you'd want to specify the domain and port for the application to run on.
2. Run `pinniped provision` to create an EC2 instance.
3. Run `pinniped deploy` to deploy your application to an EC2 instance.

After the following steps are finished, your application is deployed on an AWS EC2 instance. To monitor the backend, you can go to your admin dashboard at the relative path, `/_`, of your host.

### Managing Your Application
To start your application on EC2, run `pinniped start`.

Similarly, to stop your application, run `pinniped stop`.

If you need to update your application, i.e., adding function handlers for custom events, then run `pinniped update` to push the local changes in your project directory to the EC2's local directory.
