# AutoBidder-for-VastAI-instances
Bid automatically on gpu instances for cheapest prices to deploy ml models

This project contain script to bid on vast ai (https://vast.ai) and maintain at lease one instance running to deploy deep learning models on gpu instances.

### Features

1.Search for existing running instances

2.Launch new existing instances with their base price or provided from cli

3.Destroy instances if running more than 1

### Usage

1.install [vast ai cli](https://vast.ai/console/cli/)

2.Login via cli

3.Put this script in any environment path(for linux its usually /usr/bin/) Then run
```
vast one-alive --onstart="path-to-onstart-script"
```

4.This script can run in background in your own mahcine or on aws t2.micro to run in continuously check instance status.
for this make a cron job.

5.Usually onstart script clones a project from github and setups server accordingly with running main application in background and returning to cli

6.Example onstart script to run my project [Spleeter-Deploy](https://github.com/mayurnewase/Spleeter-Deploy) which runs telegram server in background
```
apt-get install ffmpeg --assume-yes
apt install git --assume-yes
git clone https://github.com/mayurnewase/Spleeter-Deploy.git
cd Spleeter-Deploy/
pip install -r requirements.txt
echo "bot_token=<your token>" > .env
nohup python application.py &
```
