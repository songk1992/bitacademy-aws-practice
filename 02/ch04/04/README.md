## 예제 실행 (AWS에 stack 생성하기)

### ex03

```bash

주소 = https://github.com/songk1992/bitacademy-aws-practice/blob/main/02/ch04/04/ex03.json
키페어키값 = ec2_learn_0814_dell_Insp
VPC값=vpc-27cb4b4c


aws cloudformation create-stack --stack-name myserver --template-body 주소 --parameters ParameterKey=KeyName,ParameterValue=키페어키값 ParameterKey=VPC, ParameterValue=VPC값 ParameterKey=InstanceType,ParameterValue=t2.micro

$ aws cloudformation describe-stacks --stack-name myserver --query Stacks[0].Outputs

$ aws cloudformation delete-stack --stack-name myserver


```
