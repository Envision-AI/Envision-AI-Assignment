# Envision Livekit Assignment

# Assignment
Here in Envision we are working on making a real-time personalized assistant for the blind and visually impaired called Ally. This assistant works in a way that is intuitive. Ally understands what the user is trying to do and assists them in a way that makes their day to day lives easier in a seemless and conversational way. 

However we are facing one particular problem with Ally. Proprietary models such as gpt-4o decline to answer image questions when there is a person in the frame due to guardrails put to preserve private information. We want you to come up with a system using this codebase to find out when there is a person in the frame and use an open source LLM model in those cases. The open source model should only trigger in the case of there being a person in the frame and it should describe the entire image including the person accurately and in good detail while keeping the latency to minimum.

Evaluation will be based mostly on reliability and speed. Please provide a README file so we can easily run your code.
success criteria:
- Answer at least 10 image questions in the same call, without degradation in response times, with an equal split of images featuring people and those that do not.
- The implemented model should be streamed and have Time to first Token of <500ms.
- Ensure images are captured reliably when necessary and intended.
- README file should be in a way that lets us run the project with as little modifications as possible.


PS: You will need to change the provided code to get the best performance.

# Setup

First, create a virtual environment, update pip, and install the required packages:

```
$ python3 -m venv ally_env
$ source ally_env/bin/activate
$ pip install -U pip
$ pip install -r requirements.txt
```

You need to set up the following environment variables:

First make a free account on livekit and get your own Livekit url, api key and secret.
The other 3 api keys are in the password protected zip file, the password is in the email sent to you.

```
LIVEKIT_URL=...
LIVEKIT_API_KEY=...
LIVEKIT_API_SECRET=...
DEEPGRAM_API_KEY=...
OPENAI_API_KEY=...
ELEVEN_API_KEY=
```

Then, run the assistant:

```
$ python3 assistant.py download-files
$ python3 assistant.py start
or
$ python3 assistant.py dev
```

Finally, you can load the [hosted playground](https://agents-playground.livekit.io/) and connect it.

And most of all have fun with it :)
