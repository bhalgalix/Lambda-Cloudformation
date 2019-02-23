<h2> Lambda-Cloudformation </h2>

This is a tutorial to create a lambda function via Amazon Cloud formation.

For this tutorial you will need to have an AWS(Amazon Web Services) account. For this, go to <a href="https://aws.amazon.com/" target="_blank">AWS</a> and create a free account.

<h3>"Coding" the files</h3>


Next you need to create a new file in a text editor like <a href="https://www.sublimetext.com/" target="_blank">Sublime Text</a> or Notepad. You will paste this <a href="https://github.com/bhalgalix/Lambda-Cloudformation/blob/master/hello-world-lambda.py" target="_blank">code</a> and save it with .py format. Example: my-lambda.py.

You will compress this file to have a .zip file that you will later use. This zip file can have any name but don't use anything too complex because you will write it later.

<h3>Creating a Bucket</h3>

Next go to <a href="https://s3.console.aws.amazon.com/s3/" target="_blank">Amazon S3</a>. Here, you will create a bucket to upload you zip file.

First, click the blue button **+ Create Bucket**.

A window will pop and ask you a name for your new bucket. This name must be unique in all Amazon s3 so use something like "bhalgalix-lambda-code" changing for your username at the beginning. 

Click **Next**.

All the other option options are not necessary for this tutorial so you can click next in all the other steps and Create Bucket at the end.

Now that your bucket is created click in it and inside the bucket click the option **Upload**.

Select the zip file you previously created and click **Next**.

We don't need to do anything else in the other steps neither so just click **Next** and **Upload** at the end.

The s3 Bucket is ready.

<h3> Creating a Role to access the bucket </h3>

Go to <a href="https://console.aws.amazon.com/iam/" target="_blank">IAM</a>.

In the left pannel go to **Roles**. 

Click on **Create Role**.

In the "Service that will use this role" choose **Lambda** and click **Next: Permissions**.

In the next step you will select "AdministratorAccess", this will give you access to all the services so you don't worry about permission policies.

Click **Next: Tags**, in this step you don't need to add any tag, just click **Next:Review**.

In the final step you need to name your new role and click **Create Role**. 

Now your role is created and you should see it in the list. Click in it, and the Summary look for the Arn. This is like a codebar for any resource you have in Amazon.

You will use this later to give access to the S3 Bucket.

<h3> Using templates to create the Lambda </h3>

For the final step we will go to <a href="https://console.aws.amazon.com/cloudformation/
" target="_blank">Cloudformation</a>. We will design a template that will use the zip file in the bucket you created to get new Lambda functions. 

Click on **Design Template**.

In the options at the left look for the "Lambda" option and from this drag the option "Function" to the center of the screen.

At the botton of the screen you will paste the code of the <a href="https://github.com/bhalgalix/Lambda-Cloudformation/blob/master/code.json" target="_blank">.json file</a> and you will change some things.

First you will change the name of the template. In the example code it is called "Lambda1".

Next change the name of the S3 Bucket name for the S3 Bucket you created moments ago. In the example code change "felix-lambda-code".

Change the S3 Key for the name of your zip file stored in the S3 Bucket. In the example code change "hello_lambda.zip"

Change the FunctionName. This name needs to be unique so take that into account when changing it. In the example code the FunctionName is "Felix-hello-world1234".

Last you will change the role for the Arn of the role you just created. In the example code the Role is "arn:aws:iam::776831754616:role/testRol".

Now you can validate your template with the button with the check at the top left and if everything is ok you can **Create Stack** (button with the cloud and up-arrow).

Click **Next**.

In this step you will give your stack a name. This name will not change the name of your lambda function so you use something like "CreateLambda" for you to remember what it does.

Click **Next**.

Click **Create**.

Now your lambda function is being created. If there are no problems after a short while in the status tab it will say "CREATE-COMPLETE".

You can go to <a href="https://console.aws.amazon.com/lambda/" target="_blank">AWS Lambda</a> to see your new lambda funcion.





