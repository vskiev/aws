aws ec2 describe-instances

aws ec2 start-instances --instance-ids i-dddddd70

aws ec2 stop-instances --instance-ids i-5c8282ed

aws ec2 terminate-instances --dry-run --instance-ids i-dddddd70

aws ec2 create-tags --resources i-dddddd70 --tags Key=Department,Value=Finance

aws ec2 describe-volumes 

aws ec2 attach-volume  --volume-id vol-1d5cc8cc --instance-id i-dddddd70 --device /dev/sdh

aws ec2 run-instances --dry-run --image-id ami-08111162 --count 1 --instance-type t1.micro --key-name MyKeyPair --security-groups my-ami-security-group

aws ec2 reboot-instances --instance-ids i-dddddd70 

aws ec2 modify-instance-attribute --instance-id i-44a44ac3 --instance-type "{\"Value\": \"m1.small\"}"

aws ec2 create-image --instance-id i-44a44ac3 --name "Dev AMI" --description "AMI for development server"

aws ec2 describe-images --image-ids ami-2d574747

aws ec2 deregister-image --image-id ami-2d574747 && aws ec2 delete-snapshot --snapshot-id snap-4e665454

aws ec2 delete-snapshot --snapshot-id snap-4e665454

aws ec2 modify-instance-attribute --instance-id i-44a44ac3 --disable-api-termination

aws ec2 modify-instance-attribute --instance-id i-44a44ac3 --no-disable-api-termination

aws ec2 get-console-output --instance-id i-44a44ac3

aws ec2 monitor-instances --instance-ids i-44a44ac3

aws ec2 unmonitor-instances --instance-ids i-44a44ac3

aws ec2 describe-key-pairs

aws ec2 create-key-pair --key-name dev-servers

aws ec2 delete-key-pair --key-name dev-servers


example with tagging instance
===============================================
aws ec2 run-instances --image-id ami-abc12345 --count 1 --instance-type t2.micro --key-name MyKeyPair --subnet-id subnet-6e7f829e --tag-specifications 'ResourceType=instance,Tags=[{Key=webserver,Value=production}]' 'ResourceType=volume,Tags=[{Key=cost-center,Value=cc123}]'