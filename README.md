# Installation Script for LLaMa 4bit 128g on Ubuntu


This is an installation script - that uses bitsandbytes from TimDettmers, text-generation-webui from oobabooga and GPTQ-for-LLaMa from qwopqowp200 - for LLaMa on Ubuntu Desktop v22.04.
Although with some tweaks you may get this to work properly on another hardware or on multi-GPU setups,
these instructions are specifically designed to work with Nvidia graphics cards - and I only cover a Single-GPU configuration.
I'll be using my RTX2060 with 6GB to load Llama model 7B with 4-bit quantization,
but you can try this tutorial with other models that fit your Nvidia hardware.

----------------------------------------------------------------------------------

Youtube video:

https://www.youtube.com/watch?v=RcHIOVtYB7g

----------------------------------------------------------------------------------

These instructions are delivered for educational purposes only, and it assumes that you have a fresh install of
Ubuntu version v22.04.

While we will need to reboot Ubuntu a few times, I've done my best to simplify the instructions
to minimize the number of steps. This will help you explore these AI models as fast as possible.


----------------------------------------------------------------------------------
----------------------------------------------------------------------------------
Preliminary instructions:
----------------------------------------------------------------------------------
Open terminal:

Install git:

	sudo apt install git -y

----------------------------------------------------------------------------------

Clone repository and reboot into console mode:

	git clone -b Linux https://github.com/Highlyhotgames/fast_txtgen.git && cd fast_txtgen && chmod +x remove_gui && ./remove_gui
	
After reboot, you have two options:

For those that already have Nvidia driver installed and wants to skip driver installation:

	cd fast_txtgen && ./req_basic && ./install

For those who wants to install Nvidia driver (recommended):

	cd fast_txtgen && ./requirements

After reboot:

	cd fast_txtgen && ./install

When "checking CUDA Installation" it will display a message "release 11.7" in cyan color.


After installation is complete:

	cd fast_txtgen && ./download

Select the models by entering the numbers of the models you want from the ones the list

You can download multiple models at once separating them with spaces, eg. 1 2 4

After download is complete, exit by entering '5'

----------------------------------------------------------------------------------

Return to Ubuntu GUI:

	cd fast_txtgen && ./restore_gui

----------------------------------------------------------------------------------

Open terminal to run the webUI server:

	cd fast_txtgen && ./run

Open your browser and enter the default URL:

—> http://127.0.0.1:7860



----------------------------------------------------------------------------------
----------------------------------------------------------------------------------
If you need to edit the run script to suit your needs, run this:

	cd fast_txtgen && ./edit

----------------------------------------------------------------------------------

(example: when editing the run script you can add --listen to server.py so that you can open the chat on another device, using the Ip address of your PC rather than 127.0.0.1)

----------------------------------------------------------------------------------
----------------------------------------------------------------------------------
----------------------------------------------------------------------------------
----------------------------------------------------------------------------------
