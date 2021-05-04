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

### Override terragrunt.hcl parameters ###
```
terraform {
  extra_arguments "custom_arguments" {
    commands  = ["plan"]
    arguments = ["-out=plan.out"]
  }
  after_hook "after_hook_plan_to_json" {
    commands = ["plan"]
    execute  = ["sh", "-c", "terraform show -json plan.out > plan.out.json"]
  }
}
```

### Create all plan with terragrunt
```
$ terragrunt plan-all
```

### Create report.html
```
$ tgreport -i <PIPELINE_GILAB_ID> -u <PROJECT_GITLAB_URL>
```

## License

The source code for the site is licensed under the MIT license, which you can find in
the [LICENSE](https://github.com/sbeyn/terragrunt-report/blob/main/LICENSE) file.
