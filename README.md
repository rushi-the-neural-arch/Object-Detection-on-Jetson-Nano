# Object-Detection-on-Jetson-Nano
Building YOLO V2/V3 Object Detection on Jetson Nano



Reference Links :


https://medium.com/swlh/nvidia-jetson-nano-custom-object-detection-from-scratch-using-tensorflow-and-opencv-113fe4dba134 

https://www.dlology.com/blog/how-to-run-tensorflow-object-detection-model-on-jetson-nano/ 


Adding SwapSpace and Installing Opencv : https://pysource.com/2019/08/26/install-opencv-4-1-on-nvidia-jetson-nano/ 


Note the below steps are borrowed from https://www.pyimagesearch.com/2019/05/06/getting-started-with-the-nvidia-jetson-nano/ 

Please refer the blog for more details

Getting Started 

( This assumes you have Basic knowledge of working of Jetson Nano)

Step 1:  Download and flash the .img file to your micro-SD card

	You can use Etcher Software (preferable)


Step 2:  Installing system packages and prerequisites

             sudo apt-get install git cmake
	 sudo apt-get install libatlas-base-dev gfortran
             sudo apt-get install libhdf5-serial-dev hdf5-tools
             sudo apt-get install python3-dev


Step 3: Configure your Python Environment


	wget https://bootstrap.pypa.io/get-pip.py
	sudo python3 get-pip.py
	rm get-pip.py


	Install Virtualenv wrapper

	sudo pip install virtualenv virtualenvwrapper

	
	Once we’ve installed virtualenv and virtualenvwrapper we need to update our      ~/.bashrc file. I’m choosing to use nano but you can use whatever editor you are most comfortable with


	nano ~/.bashrc


	Scroll down to the bottom of the ~/.bashrc file and add the following lines:


	# virtualenv and virtualenvwrapper
	export WORKON_HOME=$HOME/.virtualenvs
	export VIRTUALENVWRAPPER_PYTHON=/usr/bin/python3
	source /usr/local/bin/virtualenvwrapper.sh



	Next, we need to reload the contents of the ~/.bashrc file using the source command:


	source ~/.bashrc


Step 4: Installing TensorFlow and Keras on the NVIDIA Jetson Nano


	workon obj_det

          pip install numpy 



          You can install the official Jetson Nano TensorFlow by using the following command:



     pip install --extra-index-url https://developer.download.nvidia.com/compute/redist/jp/v42 tensorflow-gpu==1.13.1+nv19.3      (Takes long time :) )



	 pip install scipy
	 pip install keras


Step 5: Compiling and installing Jetson Inference on the Nano
 

The first step is to clone down the jetson-inference repo:

$ git clone https://github.com/dusty-nv/jetson-inference
$ cd jetson-inference
$ git submodule update —init


We can then configure the build using cmake.


mkdir build
cd build
cmake ..


After that

make
sudo make install



 For Installing OpenCV

  Please follow this link :

 ( Use Swap Space)

https://pysource.com/2019/08/26/install-opencv-4-1-on-nvidia-jetson-nano/ 

		OR 

	https://thenewstack.io/tutorial-configure-nvidia-jetson-nano-as-an-ai-testbed/ 


