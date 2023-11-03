# This project utilizes AWS CloudFormation to set up an Auto Scaling group, an S3 Bucket, and an SNS Topic. The Auto Scaling group ensures that the desired number of instances is maintained based on configured conditions, while the S3 Bucket serves as a host for a static website. An SNS Topic is created to notify subscribers (in this case, via email) about specific events.

Components:
Auto Scaling Group: Ensures the appropriate number of instances is maintained based on conditions.
S3 Bucket: Hosts the static website files.
SNS Topic: Sends notifications to subscribed email addresses.
Instructions:
Launch Configuration: A t2.micro instance is created with a predefined user data script that installs and starts an Apache web server, and hosts a basic HTML file.

Auto Scaling Group: Spans multiple availability zones and uses the defined Launch Configuration. It maintains a minimum of 1 instance, up to a maximum of 4, with a desired capacity of 2.

Scaling Policies: Two CloudWatch Alarms are set up. One scales in if CPU usage is below 30%, and the other scales out if CPU usage is above 70%.

S3 Bucket: A bucket named nawaf-s3-bucket is created to host the static website.

SNS Topic and Subscription: An SNS Topic named nawaf-sns-topic is created. The provided email address is subscribed to this topic to receive notifications.

Access the Website:
Link to the hosted website
