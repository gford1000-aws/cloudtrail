# Cloudtrail

AWS CloudFormation script that creates an AWS CloudTrail log, and corresponding S3 bucket.

The trail may optionally stream to a LogGroup within CloudWatch, allowing alarms and/or rules to be applied.

The script creates the following:

![alt text](https://github.com/gford1000-aws/cloudtrail/blob/master/Screen%20Shot%202017-06-12%20at%203.40.47%20PM.png "Script per designer")

Notes:

1. The S3 bucket will not be deleted if the stack is deleted, so that logs are retained.
2. Only one trail is ever created (EnableCloudWatch condition determines which of the trail resources are created)


## Arguments

| Argument                   | Description                                             |
| -------------------------- |:-------------------------------------------------------:|
| EnableCloudWatch           | Whether CloudWatch logs will be created                 |
| EnableMultiRegion          | Whether the trail covers all regions                    |
| EnableLogFileValidation    | Whether hash files of the trails will be created        |
| IncludeGlobalServiceEvents | Whether global Service events are included in the trail |
| TrailName                  | Value assigned to the Name tag for the trail            |
| TrailRole                  | Value assigned to the Role tag for the trail            |


## Outputs

| Output           | Description                                |
| ---------------- |:------------------------------------------:|
| Bucket           | The S3 bucket which will contain the logs  |

## Licence

This project is released under the MIT license. See [LICENSE](LICENSE) for details.
