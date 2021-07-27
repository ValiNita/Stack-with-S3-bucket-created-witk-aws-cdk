1. Initial am folosit comenzile :
cdk init app --language python

python3 -m venv .venv

source .venv/bin/activate

python -m pip install -r requirements.txt

pip install aws-cdk.aws-s3

2. Am adaugat in app.py :

from aws_cdk import core
from aws_cdk import aws_s3 as s3


class ApplicationStack(core.Stack):

    def __init__(self, scope: core.Construct, construct_id: str, **kwargs) -> None:
        super().__init__(scope, construct_id, **kwargs)

        s3.bucket(self, "hw3nitavalentin", versioned=True, )
 3. Am folosit comanda cdk synth dupa care am folosit cdk deploy --all pt deploy.
 4. Ca ultim pas am folosit comanda aws cloudformation deploy --template-file s3bucket.yml --stack-name NewfolderStack pt a dauga s3 bucket pe stack.
 
 
 Stack ARN:
arn:aws:cloudformation:eu-west-1:932627707940:stack/NewfolderStack/fef27450-eed1-11eb-b525-02b27cf55d43
https://console.aws.amazon.com/s3/ap/932627707940/homework3?region=eu-west-1
