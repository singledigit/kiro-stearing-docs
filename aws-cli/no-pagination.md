---
title: AWS CLI Best Practices
inclusion: always
---

# AWS CLI Best Practices

## Pager Behavior

When running AWS CLI commands that might produce large outputs, always use the `--no-cli-pager` option to prevent interactive paging. This is especially important for:

- List operations (`aws s3 ls`, `aws ec2 describe-instances`, etc.)
- Commands that return large JSON responses
- Commands used in scripts or automation

Example:
```bash
aws amplify list-apps --profile da --no-cli-pager
