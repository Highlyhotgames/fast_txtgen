# Installation Script for LLaMa 4bit 128g on WSL - AMD Graphics Cards

[THIS IS UNDER DEVELOPMENT AND NOT WORKING YET]
This is an installation script - that uses bitsandbytes from TimDettmers, text-generation-webui from oobabooga and GPTQ-for-LLaMa from qwopqowp200 - for LLaMa on your Windows machine using WSL (Windows Subsystem for Linux).
Although with some tweaks you may get this to work properly on another hardware or on multi-GPU setups,
this installation script is specifically designed to work with AMD graphics cards - and I only cover a Single-GPU configuration.

----------------------------------------------------------------------------------

Youtube video:

https://www.youtube.com/watch?v=RcHIOVtYB7g

----------------------------------------------------------------------------------

These instructions are delivered for educational purposes only, and it assumes that you have a fresh install of
windows 10/11 latest version (and it is obvious that you can try it without having to reinstall Windows).

While we will need to restart the Ubuntu terminal a few times, I've done my best to simplify the instructions
to minimize the number of steps. This will help you explore these AI models as fast as possible.


----------------------------------------------------------------------------------
----------------------------------------------------------------------------------

Software requirements:
----------------------------------------------------------------------------------

Open windows update (right-click on start menu; settings; update & security), click on advanced options and
enable “receive updates for other Microsoft products when you update Windows”, then
check for updates and restart your PC if required.

Go to nvidia website (or through your Geforce Experience app if u have installed) and install latest version
of your nvidia driver (make sure it is the “Game ready” version), restart again if required.

----------------------------------------------------------------------------------
----------------------------------------------------------------------------------
----------------------------------------------------------------------------------

Instructions:
----------------------------------------------------------------------------------

Click on start menu; type cmd and click on “run as administrator”

	wsl --install

It will ask to restart PC if this is the first WSL installation on this machine

After reboot WSL will continue installation...

While it does, click on start menu; type cmd and open

	notepad .wslconfig

Click on yes to create a new file; copy and paste the content below:


	[wsl2]
	memory=6GB
	processors=2
	swap=20GB
	localhostforwarding=true
		
Change memory and swap sizes to match the models you will test (or hardware capabilities) following this list:
	
7B -> 6GB/20GB

13B -> N/A / N/A

30B -> N/A / N/A

65B -> N/A / N/A

Close notepad, click on save; close prompt;

When WSL installation ends, enter a username and a password, then run this command:


	git clone https://github.com/Highlyhotgames/fast_txtgen.git > /dev/null 2>&1 && cd fast_txtgen && chmod +x requirements && ./requirements
	


Enter password and wait for message to close terminal; close

To ensure WSL2 is activated and to update:

Click on Start menu; type cmd and run as Administrator



	wsl --set-version Ubuntu 2 & wsl --update & wsl --shutdown & exit


Open windows update and check for updates - it will get an update for WSL;

Open Ubuntu, type:


	cd fast_txtgen && ./install
	



After installation is complete:

	cd fast_txtgen && ./download

Select the models by entering the numbers of the models you want from the ones the list

You can download multiple models at once separating them with spaces, eg. 1 2 4

After download is complete, exit by entering '5'

To run the webUI server:

	cd fast_txtgen && ./run

Default URL:

—> http://127.0.0.1:7860

----------------------------------------------------------------------------------
----------------------------------------------------------------------------------
----------------------------------------------------------------------------------

If u closed and want to run again, open Ubuntu and paste this command:

	cd fast_txtgen && ./start

----------------------------------------------------------------------------------
----------------------------------------------------------------------------------
----------------------------------------------------------------------------------
If you need to edit the run script to suit your needs, run this:

	cd fast_txtgen && ./edit

----------------------------------------------------------------------------------
----------------------------------------------------------------------------------
----------------------------------------------------------------------------------
To remove completely (including WSL), open cmd as Admin:

	wsl --shutdown & wsl --unregister Ubuntu

----------------------------------------------------------------------------------
----------------------------------------------------------------------------------
----------------------------------------------------------------------------------
----------------------------------------------------------------------------------
