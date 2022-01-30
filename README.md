# Terragrunt-report

Report infrastructure changes as code with Terragrunt

## Requirements

| Name | Version |
|------|---------|
| python | 3.6 |
| terragrunt | 0.24.1 |

## Install

```
$ python setup.py install
```

## Usage

### Create a plan with terragrunt
```
$ cd project/main
$ terragrunt plan-all -out=plan.out
```

### Create report.html
```
$ tgreport -i <ID> -u <URL>

or

$ tgreport -i <ID> -u <URL> -m "*pass*,*secret*,*token*,*access*,*result*,*certs*,*certificate*,*rsa*,*dsa*,*private*,*salt*,*hash*,*vars*,*triggers*"
```
