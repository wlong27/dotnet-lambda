aws sso login --profile <sso-profile-name>

# AWS SSO
Create new sso profile. User will be prompted from browser.
```bash
aws configure sso
```

Check that profile is saved successfully
```bash
aws configure sso list-profiles
```
You can use any profile that is saved by specifying the profile name.
```bash
aws s3 ls --profile my-sso-profile
```