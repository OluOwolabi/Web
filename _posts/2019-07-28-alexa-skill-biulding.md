---
layout: post
title: "How to build a skill with Alexa"
date: 2019-07-28
author: Olu Owolabi
---
[//]: <> ![alexa](/files/alexa.png)

# **Alexa**
Nowadays, most in-home tasks and daily activities are completed using voice commands/interactions. These activities ranges from flights bookings to music playback to setting alarms to listening to news/sports update to making-to-do list to shopping and lot more. This is where Amazon Alexa comes in play -- Alexa in Short, is a virtual assistant that uses voice interaction to complete tasks for us. Overtime Alexa has been able to do more than just complete tasks for us, it is being used to control several smart devices and it's being used as an home automation system. Users are also able to extend Alexa capabilities by building [skills](https://developer.amazon.com/en-US/alexa/alexa-skills-kit) to it. These skills can be used to serve customers naturally, expand your reach, and even make money. Depending on you technology expertise, you can build skills for Alexa by [coding it yourself](https://developer.amazon.com/docs/ask-overviews/build-skills-with-the-alexa-skills-kit.html) using the Amazon Alexa API, or you can [hire an agent](https://developer.amazon.com/alexa/agencies-and-tools) to do the building for you, and in a more simpler way, you can always fill a [blueprint template](https://blueprints.amazon.com/) created for building skills by Amazon. In this post, I will be showing you how to build a skill for Alexa. With this knowledge, you can decide if you want to monetize you skill, or just do if for the fun. Without wasting time, let's get into it.

# **Things needed to build skills for Alexa**
To build your skills for Alexa, here are some of the few tools you will need to get started;

* [Amazon developers account](https://developer.amazon.com/alexa/console/ask): To get started with building skills for Alexa, you need to create a **FREE** developer account with Amazon. In this process you can use your existing amazon account or decide to create a new Amazon developer account by providing basic information about yourself.

* [Amazon Web Services (AWS) Lambda account](https://portal.aws.amazon.com/billing/signup#/start): AWS Lambda is a service that lets you run code in the cloud without managing servers. Alexa sends your code user requests and your code can inspect the request, take any necessary actions and then send back a response. You can write Lambda functions in Node.js, Java, Python, C#, or Go.

* [Alexa Device](https://www.amazon.com/Amazon-Echo-And-Alexa-Devices/b?ie=UTF8&node=9818047011): Although this item is optional, however, if you would like to test your skills in real time, it is advisable to get an Alexa device.

# **Your** [Amazon developers account](https://developer.amazon.com/alexa/console/ask)
Once you've created your Amazon developer account, below are some steps to get you started on building your skill;
![alexa](/files/alexa/1.png)

<pre>Click on <b>amazon Alexa</b>.
</pre>

![alexa](/files/alexa/2.png)

<pre>Click on <b>Create Alexa Skills</b>.
</pre>

![alexa](/files/alexa/3.png)

<pre>Click on <b>Start a Skill</b>.
</pre>
![alexa](/files/alexa/4.png)

<pre>Click on <b>Create Skill</b>.
</pre>

![alexa](/files/alexa/5.png)
![alexa](/files/alexa/6.png)

<pre>Choose a <b>Name</b> for your skill.

Select <b>Custom</b> model to add to skill.

Select <b>Alexa-Hosted</b> as the method to host your skill's backend resources.
</pre>

# **Your Skill**
In this example, I would be building a very simple skill that tell you facts about puppies. I have named this skill sayHello,
![alexa](/files/alexa/7.png)

and this is what the developer console looks like once the skill has been created.

![alexa](/files/alexa/8.png)


The first step in this skill is to determine the **Invocation** for your Skill. Users say a skill's invocation name to begin an interaction with a particular custom skill. For instance, if the invocation name is "Puppies Fact ", users can say:

> User:  Alexa, get Puppies Fact to tell me about my Puppy


> User:  Alexa, Open Puppies Fact

You can change your invocation name at any time while developing a skill. You cannot change the invocation name after a skill is certified and published.

Note that the invocation name is only needed for custom skills. If you are using a pre-built model, users do not need to use an invocation name for the skill

![alexa](/files/alexa/9.png)

<pre>Describe your <b>Skill invocation Name</b>.
Click on <b>Save Model</b>
</pre>


Next, we need to create our custom **Intents, Utterances**, and **Slots**. An **intent** represents an action that fulfills a user's spoken request. Intents can optionally have arguments called **slots**. The sample **utterances** are set of likely spoken phrases mapped to the intents.

* The intent we would be creating would be called **AboutPuppies**. After the intent had been created, we would list different utterances the user would also say to invoke this intent.   
![alexa](/files/alexa/10.png)

<pre>Click on <b>Add</b> new Intent.
</pre>

![alexa](/files/alexa/11.png)

<pre>Name it what you wish.
Click on <b>Create Custom Intent</b>
</pre>

![alexa](/files/alexa/12.png)

<pre>Think of any Utterances you could say pertaining to knowing about puppies
For instance, "Alexa, Tell me about German Shepard"
<i>Note</i>: You can/need to add as many utterances given the flexibility and variation
of spoken language in the real world, there will often be many different ways to
express the same request
</pre>

* Once you have written a few utterances, note the words or phrases that represent variable information. These will become the intent's slots. For instance, we know German Shepard, Pit Bull, Bull Dog are all example of puppies. Instead of typing all type of dog breeds, you can create a slot called **puppies** to hold this variable.

![alexa](/files/alexa/13.png)

<pre>Click on <b>Add</b> new Slot.
</pre>

![alexa](/files/alexa/14.png)

<pre>Name it what you wish.
Click on <b>Create Custom slot type</b>
</pre>

![alexa](/files/alexa/16.png)

<pre>Give as many <b>value</b> you wish to add.
</pre>

![alexa](/files/alexa/15.png)

<pre>Go back to the <b>Intent</b> you created.
</pre>

![alexa](/files/alexa/17.png)

<pre>Now you can use the <b>slot</b> you just created.
<i>Note</i>: <b>Slots</b> replaces the original value in the utterance with
the slot name in curly brackets ({ }).
</pre>

![alexa](/files/alexa/18.png)

<pre>Click on <b>Save Model</b>.
Click on <b>Build Model</b>.
</pre>


# **Interfaces settings**

Depending on the skill you will be building, you will need to choose the Interfaces on which your skill interaction would take place. Because, we are building a simple skill and depending on your Alexa device we would be using the three interfaces;
* **Audio Player**: The AudioPlayer interface provides directives and requests for streaming audio and monitoring playback progression.
* **Display Interface**: Echo Show allows skill developers to create skills for Alexa that use both screen and voice interaction.
* **Video App**: The VideoApp interface provides the VideoApp. Launch directive for streaming native video files in Echo Show.

![alexa](/files/alexa/19.png)

<pre>Enable the <b>Audio Player</b>.
Enable the <b>Display Interface</b>.
Enable the <b>Video App</b>.
Click on <b>Build Model</b>.
</pre>

# **Endpoint settings**
The Endpoint will receive POST requests when a user interacts with your Alexa Skill. The request body contains parameters that your service can use to perform logic and generate a JSON-formatted response. One of the recomended **Service Endpoint** is the [AWS Lambda ARN](https://aws.amazon.com/lambda/). To get started with the [AWS Lambda ARN](https://aws.amazon.com/lambda/), you need to create a [AWS account](https://portal.aws.amazon.com/billing/signup#/start).

![alexa](/files/alexa/20.png)

<pre>Fill out the necessary information
</pre>

![alexa](/files/alexa/21.png)

Once you've created the account

<pre>Click on <b>Services</b>.
Search and click on <b>Lambda</b>.
</pre>

![alexa](/files/alexa/22.png)

<pre>Click on <b>create function</b>.
</pre>

![alexa](/files/alexa/23.png)

In the Lambda Service

<pre>Click on <b>Browse serverless app repository</b>.
Click on <b>alexa-skill-kit-nodejs-factskill</b>.
</pre>

![alexa](/files/alexa/24.png)

<pre>Click on <b>Deploy</b>.
<i>Note</i>: Application name can be changed too.
Make sure your <b>Region</b> is set to your current/closest region
</pre>

![alexa](/files/alexa/25.png)

Once application has been deployed

<pre>Click on <b>alexa-skill-kit-nodejs-factskill</b>.
</pre>

![alexa](/files/alexa/26.png)

<pre>Scroll down to the code section.
<i>Note</i>: This is where all the Handler and Intent code are being deployed from to your skill.
</pre>

# **Next Steps**
Clear the code in the new Lambda function you just created

![alexa](/files/alexa/27.png)

Now go the tool [Alexa code generator](http://alexa.codegenerator.s3-website-us-east-1.amazonaws.com/) in a new tab. The [Alexa code generator](http://alexa.codegenerator.s3-website-us-east-1.amazonaws.com/)  will basically take the JSON representation of your skills intents and create a Node.js code.

Go back to your developer site and **click on the JSON Editor** tab

![alexa](/files/alexa/28.png)

In the JSON Editor tab

<pre>Copy the JSON code.
</pre>


![alexa](/files/alexa/29.png)

Go to the [Alexa code generator](http://alexa.codegenerator.s3-website-us-east-1.amazonaws.com/) tab and

<pre>Paste the JSON code in the <b>Language Model JSON</b>.
Then click on <b>GENERATE CODE</b> to generate a Node.js code.
</pre>

![alexa](/files/alexa/30.png)

Copy the Node.js code and paste it in your empty Lambda function

![alexa](/files/alexa/31.png)

<pre>Paste the Node.js code in the empty Lambda function.
Click <b>Save</b>
</pre>

![alexa](/files/alexa/32.png)

<pre>Copy the <b>ARN</b> (Amazon resource name) at the top part of your Lambda Function
</pre>

![alexa](/files/alexa/33.png)

<pre>Back in the Alexa developer site click on the Endpoint tab
Paste the <b>ARN</b> (Amazon resource name) in the <b>Default Region</b>.
Click on <b>Save Endpoints</b>
</pre>

# **ACCOUNT LINKING AND PERMISSIONS**
If you are developing a skill that will require you to link external account or would require permissions such as location and name, then you want to go into this section. If not, you are ready to test your skills.


# **Testing your skill**

![alexa](/files/alexa/34.png)

<pre>Click on <b>Test</b> at the top part of the developer site.
</pre>

![alexa](/files/alexa/35.png)

<pre><b>Allow</b> the website to use your microphone.
</pre>

![alexa](/files/alexa/36.png)

<pre>Select <b>Development</b> in the <i>Skill testing is enabled in</i>.
</pre>

![alexa](/files/alexa/37.png)


To put your skill into interaction test with Alexa

<pre>Type <b>open</b> <i>"your invocation name"</i>.
<i>Note</i>: To get it to work perfectly, you have to follow this rule.
If you forget your invocation name, you can always go back and look it up.
</pre>

![alexa](/files/alexa/9.png)


If Alexa responds to you interaction by saying
>hello and welcome to <i>"your invocation name"</i> ! Say help to hear some options.

then your skill is up and live.

# **What Next**
Now that your skill is up and live, you can start to modify the Lambda function code to your preferences. You can start by changing the default response you get from the intents in lambda code, to anything you want.
* Let's start with the **Launch request** Handler. This handler is what Alexa would say back to you anytime you open your skill. We can modify this handler to give out some information about what our skill does.

![alexa](/files/alexa/38.png)

<pre>In the Lambda function, look for
<b>const LaunchRequest_Handler</b>
Then change the <b>say</b> variable into an detailed information of what your skill does.
Click on <b>Save</b>.
</pre>

Back in the Alexa developer console

![alexa](/files/alexa/39.png)

<pre>Type <b>stop</b>.
Then type <b>open</b> <i>"your invocation name"</i>.
<i>Note</i>: If you don't notice any changes, go back to the Lambda code. Save
and try this step on more time
</pre>

* Let's do the **Cancel Intent** Handler. This handler is what Alexa would say back to you anytime you decide to stop/close your skill. We can modify this to say something nice when prompted to stop.

![alexa](/files/alexa/40.png)

<pre>In the Lambda function, look for
<b>const AMAZON_CancelIntent_Handler</b>
Then change the <b>say</b> variable into something nice.
Click on <b>Save</b>.
</pre>

Back in the Alexa developer console

![alexa](/files/alexa/41.png)

<pre>Type <b>stop</b>.
Then type <b>open</b> <i>"your invocation name"</i>.
Type <b>cancel</b>.
<i>Note</i>: If you don't notice any changes, go back to the Lambda code. Save
and try this step on more time
</pre>

* Now let's work on the **Custom Intent**. This intent will be modified depending on what your skill is doing. In this case, since we have a slot and different utterances on how the skill would be called. A little bit of coding experience would be needed.  

![alexa](/files/alexa/42.png)

<pre>In the Lambda function, look for
<b>const  "your custom Intent"_ Handler</b>
Then delete all the highlighted part of the code above
Click on <b>Save</b>.
</pre>.

![alexa](/files/alexa/43.png)

<pre>In the custom Intent"_ Handler function
Declare <b>say</b> variable as an empty string ('')
Create an <b>if-else</b> conditional statement.
In your <b>if</b> block, let your <b>condition</b> be
<b>(slotValues && slotValues.'slotName')</b>
You can decide what Alexa response should be with the <b>say</b> variable.
In your <b>else</b> block,
Just make Alexa respond if the statement said can't be found in the slot your created
Click on <b>Save</b>.
</pre>

![alexa](/files/alexa/44.png)
Back in the Alexa developer console

<pre>Type <b>open</b> <i>"your invocation name"</i>.
Type one of the utterances you declared when creating the skill and wait for Alexa
to respond with the response you just defined in the custom intent.
</pre>


In conclusion, this is just a beginners guide on how to build a skill for Alexa. This should at least get you going. Depending on what you want to use this skill for, you can always work on this tutorial to perfect your skills. To learn more you can always go to the Amazon [Alexa Skill kit](https://developer.amazon.com/alexa) to learn more.
