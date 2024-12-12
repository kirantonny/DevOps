# Pull Request Review Validations.
## For any bucket changes:
- [] Please attach screenshot of S3 Bucket Policy validation evidence from Triton: [validation here] (https://triton.cloud.capitalone.com/policy-validator)
## For Non Prod Buckets please leverage jenkins to perform validations on your pull request:
- [] Please navigate to PR Build in Jenkins ([Card Recoveries] (https://cardrecoveriesjenkins.cloud.capitalone.com/job/Bogie/job/cure-horizontal/job/cure-horizontal-s3-buckets/view/change-requests/) / [Card Core] (https://cardcorejenkins.cloud.capitalone.com/job/Bogie/job/cure-horizontal/job/cure-horizontal-s3-buckets/view/change-requests/)).
### Lint CFT:
- [] Please attach screenshot of local linting validation:
Install "cin-lint" using "brew install cfn-lint
Download 'capp-custom-resource-lint-rules.txt* from [here] (https://github.cloud.capitalone.com/bogie/jenkins-pipeline-library/blob/master/resources/capp-custom-resource-lint-rules.txt).
Run the below command to lint the CFT;
cin-lint --template «your-cft-yaml-file> -format pretty --custom-rules capp-custom-resource-lint-rules. Act
- [1 Please attach screenshot of CFT validation:
#### Validate CFT
Run the below command to validate the CFT:
aws cloudformation validate-template -template-body file://<your-cft-yaml-file>
