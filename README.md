# Blockwage Masternode Tutorial

# 1. -- Getting Ready --

1. Generate a new receiving address in the BWG wallet

2. Send 2,500 BWG to the address you generated

3. Generate a private key:

	Go to Tools -> Debug
	
	Enter ```masternode genkey```
	
	Save this as your private key
	
4. Wait until your transaction has confirmed and type ```masternode outputs``` in the debug console

	Save the long string and the ```0``` or ```1``` as these are your transaction ID and index

# 2. -- Configuring Your VPS --

1. Launch an Ubuntu 16.04 64 bit VPS from your favorite provider

2. Login to your VPS via SSH Terminal (Like Putty) and enter the following:

	```apt-get update -y && apt-get upgrade -y && wget https://raw.githubusercontent.com/blockwage/bwg-node/master/bwg-mn.sh && bash bwg-mn.sh```
	
3. Paste your private key that you generated previously when asked for it

4. Copy your IP and private key for the masternode configuration file in the next portion

# 3. -- Setting Up Your Configuration --

1. Open your wallet and go to Tools -> Open Masternode Configuration - Open this with Notepad if it asks

2. Enter your configuration line based off of the example given

	Replace the IP with your IP from your VPS
	
	Replace the next portion which is the private key with your own
	
	Replace the next portion with the transaction ID that you were provided with in the first step
	
	Replace the index ID with what you were provided with in the first step
	
3. Once this is complete, save the file and restart your wallet

4. After 15 confirmations have passed, go to Tools -> Debug and enter

	```masternode start-alias alias 'alias'``` with 'alias' being the name you gave it in the configuration file, likely mn1 without the ' '
	
5. Enjoy!
