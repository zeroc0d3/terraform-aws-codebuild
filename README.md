<!-- This file was automatically generated by the `build-harness`. Make all changes to `README.yaml` and run `make readme` to rebuild this file. -->

[![Slalom][logo]](https://slalom.com)

# terraform-aws-codebuild [![Build Status](https://travis-ci.com/JamesWoolfenden/terraform-aws-codebuild.svg?branch=master)](https://travis-ci.com/JamesWoolfenden/terraform-aws-codebuild) [![Latest Release](https://img.shields.io/github/release/JamesWoolfenden/terraform-aws-codebuild.svg)](https://github.com/JamesWoolfenden/terraform-aws-codebuild/releases/latest)

Terraform module to provision an AWS [`codebuild`](https://aws.amazon.com/codebuild/) CI/CD system.

---

This project uses the "build-harness" a modified version of the project ["SweetOps"](https://cpco.io/sweetops) from Cloudposse. Sweet indeed.

It's 100% Open Source and licensed under the [APACHE2](LICENSE).

## Usage

Include this repository as a module in your existing terraform code:

```hcl
module "codebuild" {
  source     = "git::https://github.com/jameswoolfenden/terraform-aws-codebuild.git?ref=master"

  depends_on      = ["${aws_iam_group.developer.group_name}"]
}
```

## Detailed Notes
These template inplment the module terraform-aws-codebuild. It includes a number of default behaviours.

### Sample buildspec files
In this example directory there is `buildspec.yml` and `buildno.sh`. These are starter build spec files you can add to the root of your new repository in CodeCommit. The `buildno.sh` shell script calls ssm and increments the build number found at that location it is then made available in the build process itself.
## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|:----:|:-----:|:-----:|
| build_timeout | The time to wait for a CodeBuild to complete before timing out in minutes (default: 5) | string | - | yes |
| common_tags | An AWS tagging scheme | map | - | yes |
| depends_on | This is a way to make a module depends on, which isnt built to depend on | list | `<list>` | no |
| description | Description of the Codebuild project | string | `` | no |
| environment | The environment being deployed | list | - | yes |
| force_artifact_destroy | Force the removal of the artifact S3 bucket on destroy (default: false). | string | - | yes |
| name | The name of the Build | string | - | yes |
| projectroot | The name of the parent project for SSM | string | - | yes |
| region | Which aws region this is in. | string | `eu-west-1` | no |
| sourcecode | The SourceCode | list | - | yes |

## Outputs

| Name | Description |
|------|-------------|
| artifact_bucket | - |
| codebuild_role | - |
| codebuild_role_name | - |

## Related Projects

Check out these related projects.

- [terraform-aws-codecommit](https://github.com/jameswoolfenden/terraform-aws-codebuild) - Storing ones code

## Help

**Got a question?**

File a GitHub [issue](https://github.com/jameswoolfenden/terraform-aws-codebuild/issues).

## Contributing

### Bug Reports & Feature Requests

Please use the [issue tracker](https://github.com/jameswoolfenden/terraform-aws-codebuild/issues) to report any bugs or file feature requests.

## Copyrights

Copyright © 2019-2019 [Slalom, LLC](https://slalom.com)

## License

[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)

See [LICENSE](LICENSE) for full details.

    Licensed to the Apache Software Foundation (ASF) under one
    or more contributor license agreements.  See the NOTICE file
    distributed with this work for additional information
    regarding copyright ownership.  The ASF licenses this file
    to you under the Apache License, Version 2.0 (the
    "License"); you may not use this file except in compliance
    with the License.  You may obtain a copy of the License at

      https://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing,
    software distributed under the License is distributed on an
    "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY
    KIND, either express or implied.  See the License for the
    specific language governing permissions and limitations
    under the License.

### Contributors

  [![James Woolfenden][jameswoolfenden_avatar]][jameswoolfenden_homepage]<br/>[James Woolfenden][jameswoolfenden_homepage] |

  [jameswoolfenden_homepage]: https://github.com/jameswoolfenden
  [jameswoolfenden_avatar]: https://github.com/jameswoolfenden.png?size=150

[logo]: https://gist.githubusercontent.com/JamesWoolfenden/5c457434351e9fe732ca22b78fdd7d5e/raw/15933294ae2b00f5dba6557d2be88f4b4da21201/slalom-logo.png
[website]: https://slalom.com
[github]: https://github.com/jameswoolfenden
[linkedin]: https://www.linkedin.com/company/slalom-consulting/
[twitter]: https://twitter.com/Slalom

[share_twitter]: https://twitter.com/intent/tweet/?text=terraform-aws-codebuild&url=https://github.com/jameswoolfenden/terraform-aws-codebuild
[share_linkedin]: https://www.linkedin.com/shareArticle?mini=true&title=terraform-aws-codebuild&url=https://github.com/jameswoolfenden/terraform-aws-codebuild
[share_reddit]: https://reddit.com/submit/?url=https://github.com/jameswoolfenden/terraform-aws-codebuild
[share_facebook]: https://facebook.com/sharer/sharer.php?u=https://github.com/jameswoolfenden/terraform-aws-codebuild
[share_googleplus]: https://plus.google.com/share?url=https://github.com/jameswoolfenden/terraform-aws-codebuild
[share_email]: mailto:?subject=terraform-aws-codebuild&body=https://github.com/jameswoolfenden/terraform-aws-codebuild
