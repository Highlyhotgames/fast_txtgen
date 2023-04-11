# Installation Script for LLaMa 4bit 128g on Ubuntu


This is an installation script for NVIDIA only. It uses bitsandbytes from TimDettmers, text-generation-webui from oobabooga and GPTQ-for-LLaMa from qwopqowp200 - for LLaMa on Ubuntu Desktop v22.04.
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

Open terminal:

Install git:

	sudo apt install git -y

----------------------------------------------------------------------------------

Clone repository and reboot into console mode:

	git clone -b Linux https://github.com/Highlyhotgames/fast_txtgen.git && cd fast_txtgen && chmod +x remove_gui && ./remove_gui

Install Nvidia driver and return to Ubuntu GUI:

	cd fast_txtgen && ./nv_driver && ./restore_gui

Back to Ubuntu GUI, open terminal:

	cd fast_txtgen && ./install && ./download


After download is complete, exit by entering '5'

----------------------------------------------------------------------------------


Run the webUI server:

	./run

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
