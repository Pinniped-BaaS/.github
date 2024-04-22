# Overview
Pinniped is an open-source backend that prioritizes being portable, extensible, and user-friendly. To learn more about Pinniped's development, read our case study [here](https://pinniped-baas.dev).

Pinniped is comprised of several tools, check out their READMEs after reading this overview:
 * [Core Application](https://github.com/pinniped-baas/pinniped)
 * [Admin UI](https://github.com/pinniped-baas/pinniped-admin-ui)
 * [SDK](https://github.com/pinniped-baas/pinniped-sdk)
 * [CLI Tool](https://github.com/pinniped-baas/pinniped-cli)

## Getting Started
### Prerequisites
To create a Pinniped application the following must be installed:
* Node.js

Once Node.js is installed, you can create a Pinniped application through its CLI tool.

### Install the CLI
To install the CLI tool, you can use the built-in package manager `npm`.
More information about the CLI can be found at its [repository](https://github.com/Pinniped-BaaS/pinniped-cli).

1. Run `npm install pinniped-cli -g`.

### Create a Pinniped Application
1. Go to the directory where you'd like to create your application.
2. Run `pinniped create`.

### Extend Pinniped
If you want to add custom routes and custom event handlers, check out the main documentation [here](https://github.com/pinniped-baas/pinniped).

### Deploy a Pinniped Application
Once your project is created and customized to your liking, you can move the project to a VPS that you've configured and start the server by running `index.js`.

**Alternatively, you can use the CLI tool to deploy it to AWS following these instructions:**
First, you need to set up your AWS CLI tool. The instructions can be found [here](https://docs.aws.amazon.com/cli/latest/userguide/sso-configure-profile-token.html#sso-configure-profile-prereqs).

1. Run `pinniped provision` to create and run an EC2 instance.
2. Optional: update the variables in the given `.env` file if you want to specify the domain and port for the application to run on.
3. Run `pinniped deploy` to deploy your application to an EC2 instance.

After the following steps are finished, your application is deployed on an AWS EC2 instance.

**Security**: By default the EC2 instance is configured to only accept http and https traffic (ports 80 and 443) as well as SSH traffic (port 22). Please do further security configuration and hardening of the instance as you require.

### Managing Your Application
To monitor the backend, go to your admin dashboard at the relative path, `/_`.

**If using AWS CLI deployment:**
To start your application on the provisioned EC2, run `pinniped start`.

Similarly, to stop your application, run `pinniped stop`.

If you need to update your application, i.e., adding function handlers for custom events, then run `pinniped update` to push the local changes in your project directory to the EC2's local directory.


