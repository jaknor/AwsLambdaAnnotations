# .NET Lambda Annotations Framework (Preview)

This repository showcases a bug with the .NET Lambda Annotations Framework.

If you set the template path in `aws-lambda-tools-defaults.json` to a different folder than the project with the lambdas, then the CodeUri path of the lambdas in the generated template is incorrect. The result of this is that commands such as sam build fails with an error message (`No .NET project found in directory`)

The expected result is that the CodeUri path is set relative to the template. I.E. if you set the template path to `../template.yaml` then the CodeUri would need to be `/<project-name>`