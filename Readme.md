# Winglang AWS OIDC Setup for Github Actions

This Winglang application helps you to set up AWS OpenID Connect (OIDC) for your GitHub Actions.

## Prerequisites

- You should have the Winglang CLI installed `npm install -g winglang@latest`
- Access to an AWS Account and necessary permissions to create and manage IAM Roles, Policies, and OIDC provider.

## Define Allowed Action Sources

What sources are allowed to trigger this action? Please replace `winglang/wing-github-action` with your Github repository.

```js
let subMatches = [
  // allow pull requests
  "repo:winglang/wing-github-action:pull_request",
  // allow "main" branch
  "repo:winglang/wing-github-action:ref:refs/heads/main"
];
```

For more information, please visit [Github Docs](https://docs.github.com/en/actions/deployment/security-hardening-your-deployments/about-security-hardening-with-openid-connect#understanding-the-oidc-token)

## IAM Actions

The IAM actions that this action requires is listed in the `policy` object. You can modify this as per your requirements.

## OpenID Connect Provider

An instance of the OIDC provider for GitHub Actions is created that can be deployed once per account.

## Output

The ARN of the role is provided as the output.

## Usage

1. Clone the repository to your local system.
2. Install dependencies `npm install`
2. Update the allowed sources and IAM actions as required.
3. Deploy the setup by running the Winglang application.

```
wing compile -t tf-aws main.w
cd target/main.tfaws
terraform init
terraform apply
```

## Contributing

Contributions, issues, and feature requests are welcome. Feel free to check issues page if you want to contribute.
