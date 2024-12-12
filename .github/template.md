# Pull Request Review Validations

## For Any Bucket Changes:
- [ ] Please attach a screenshot of the S3 Bucket Policy validation evidence from Triton: [Validation Link](https://triton.cloud.capitalone.com/policy-validator)

## For Non-Prod Buckets:
- [ ] Please navigate to the PR Build in Jenkins and perform validations on your pull request:
  - [Card Recoveries Jenkins Link](https://cardrecoveriesjenkins.cloud.capitalone.com/job/Bogie/job/cure-horizontal/job/cure-horizontal-s3-buckets/view/change-requests/)
  - [Card Core Jenkins Link](https://cardcorejenkins.cloud.capitalone.com/job/Bogie/job/cure-horizontal/job/cure-horizontal-s3-buckets/view/change-requests/)

### Lint CFT:
- [ ] Please attach a screenshot of the local linting validation:
  1. Install `cfn-lint` using:
     ```bash
     brew install cfn-lint
     ```
  2. Download the custom resource lint rules file from [here](https://github.cloud.capitalone.com/bogie/jenkins-pipeline-library/blob/master/resources/capp-custom-resource-lint-rules.txt).
  3. Run the following command to lint the CFT:
     ```bash
     cfn-lint --template <your-cft-yaml-file> --format pretty --custom-rules capp-custom-resource-lint-rules
     ```

- [ ] Please attach a screenshot of the CFT validation.

#### Validate CFT:
Run the following command to validate the CFT:
```bash
aws cloudformation validate-template --template-body file://<your-cft-yaml-file>
