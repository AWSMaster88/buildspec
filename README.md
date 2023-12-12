# buildspec
A sample JUnit framework for automating unit tests and generation of reports using AWS Codebuild
# Phases
You can specify the unit tests in either the build or the post_build sequence in the buildspec.yml file.
# Permissions required to have AWS Codebuild create unit test reports
To add the permissions to the existing CodeBuild projects, you need to modify the policy. Use the following IAM policy to add permissions.
#
{
    
    "Statement": [
        {
            "Resource": "arn:aws:codebuild:your-region:your-aws-account-id:report-group/my-project-*", 
            "Effect": "Allow",
            "Action": [
                "codebuild:CreateReportGroup",
                "codebuild:CreateReport",
                "codebuild:UpdateReport",
                "codebuild:BatchPutTestCases"
            ]
        }
    ]
}
